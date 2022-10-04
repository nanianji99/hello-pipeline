pipeline {
  agent {
    docker { image 'gradle:latest' }
  }
  stages {
    stage('Test') {
      steps {
        sh 'gradle --version'
      }
    }
  }
}