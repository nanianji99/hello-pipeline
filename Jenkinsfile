pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('docker')
	}

	stages {
	    
	    stage('Clone/Download') {

			steps {
				git 'https://github.com/ramdisk-ott/hello-pipeline.git'
			}
		}
		stage('Build') {

			steps {
				sh 'docker build -t rameshandroid99/pipeline:latest .'
			}
		}
	}
 

}
