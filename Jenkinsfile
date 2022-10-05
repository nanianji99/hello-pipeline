pipeline {
    agent any

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
  }
}
