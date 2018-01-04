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
	    }
	         
			
	}
