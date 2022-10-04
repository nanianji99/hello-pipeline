pipeline {
  agent {
    docker { image 'gradle:latest' }
  }
  stages {
    stage('Test') {
      steps {
        sh 'gradle --version'
		echo 'Hello, gradle'
        sh 'gradle clean'
        sh 'gradle build'   
      }
    }
  }
}