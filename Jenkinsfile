pipeline {
    agent none

  stages {
    stage('Test') {
	agent {
    docker { image 'gradle:latest' }
  		}
      steps {
		//test messa
        // sh 'gradle clean'
        sh 'gradle build'   
      }
    }
	stage('Login') {
          
			steps {
withCredentials([string(credentialsId: 'docker', variable: 'docker')]) {
   				sh "docker login -u rameshandroid99 -p  ${docker}"
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