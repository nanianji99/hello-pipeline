pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('docker')
	}

	stages {
	    
	    stage('gitclone') {

			steps {
				git 'https://github.com/ramdisk-ott/hello-pipeline.git'
			}
		}
		stage('Build') {

			steps {
				sh $PWD
				sh 'docker build -t rameshandroid99/pipeline:latest .'
			}
		}
	}
 

}
