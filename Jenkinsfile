pipeline {
    agent any

  stages {
    stage('Build') {
	agent {
    docker { image 'gradle:latest' }
  		}
      steps {
       sh 'gradle clean'
        sh 'gradle build'   
      }
    }
  }
}
