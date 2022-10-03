pipeline{

	agent any
	tools {
		  gradle "GRADLE_LATEST"
	}

	environment {
		DOCKERHUB_CREDENTIALS=credentials('docker')
	}

	stages {
	    
	    stage('Clone/Download') {

			steps {
				 git branch: 'main', url: 'https://github.com/ramdisk-ott/hello-pipeline.git'
			}
		}
		stage('Build') {

			steps {
				sh gradle --version
				//sh 'docker build -t rameshandroid99/pipeline:latest .'
			}
		}
	}
 

}
