pipeline{

	agent any
	 
	environment {
		DOCKERHUB_CREDENTIALS=credentials('docker')
	}

	stages {
	    
	    stage('Clone/Download') {

			steps {
				 git branch: 'main', url: 'https://github.com/ramdisk-ott/hello-pipeline.git'
			}
		}
	 
        stage('War Build') {
            agent { docker 'gradle:latest' } 
            steps {
                // echo 'Hello, gradle'
                // sh 'gradle clean'
                // sh 'gradle build'
            }
        }
	
stage('Login') {
          
			steps {
				 withCredentials([string(credentialsId: 'docker_password', variable: 'docker_password')]) {
   				sh "docker login -u rameshandroid99 -p  ${docker_password}"
}
				
			}
		}
stage('Docker Build & Push') {
    	agent any
      steps {
      	sh 'docker build -t rameshandroid99/pipeline:latest .'
		sh 'docker push rameshandroid99/pipeline:latest'
      }
    }
 


	}
}
