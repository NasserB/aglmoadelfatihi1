pipeline {
    agent any
    tools {
        maven 'apache-maven-3.5.0'
        jdk 'jdk1.8.0_91'
    }
    stages {
        
        stage ('Build') {
            steps {
                
                 "mvn build".execute()
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
        stage ('Test') {
            steps {
             "mvn test".execute()
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
