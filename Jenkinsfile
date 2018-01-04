	pipeline {
	    agent any
	    tools {
	        maven 'Maven 3.5.0'
        	jdk 'jdk1.8.0_91'
	    }
	    stages {
	        
	        stage ('Build') {
	            steps {
					bat 'mvn install'
	            }
	           
	        }
	        stage ('unit test') {
	            steps {
					bat 'mvn compile'
	            }
	            post {
	                success {
	                    junit 'target/surefire-reports/*.xml' 
	                }
	            }
	        }

		 
			}
			stage ('generate documentation') {
				steps {
					bat 'mvn javadoc:javadoc'
				}
				post{
					success{
						step([$class: 'JavadocArchiver', javadocDir: 'target/site/apidocs', keepAll: false])
					}
				}
			}
			stage('package'){
				steps{
					bat 'mvn package'
				}

			}
			
			
			}
	}
