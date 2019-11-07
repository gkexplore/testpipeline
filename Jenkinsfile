pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'maven_3_6_2') {
                    sh 'mvn clean compile'
                }
                script{
                     x=10
                     for(i in 0..<x){
                       println i
                     }
                 }
            }

        }

        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'maven_3_6_2') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_6_2') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}