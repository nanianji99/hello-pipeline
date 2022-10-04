pipeline {
  
  stages {
    stage('Test') {
	agent {
    docker { image 'gradle:latest' }
  }
      steps {
        sh 'gradle --version'
		echo 'Hello, gradle'
        sh 'gradle clean'
        sh 'gradle build'   
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