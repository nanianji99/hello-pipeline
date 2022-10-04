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
                echo 'Hello, gradle'
                sh 'gradle clean'
                sh 'gradle build'
            }
        }
	
stage('Login') {
            agent { label 'linux' } 

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
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
