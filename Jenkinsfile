pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'maven_3_6_2') {
                    sh 'mvn clean compile'
                }
                script{
                     def externalMethod = load("test.groovy")
                     externalMethod.exampleMethod()
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