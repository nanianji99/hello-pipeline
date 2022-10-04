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
	stage('Docker Login') {
          
			steps {
withCredentials([string(credentialsId: 'docker_password', variable: 'docker_pwd')]) {
	   				sh "docker login -u rameshandroid99 -p  ${docker_pwd}"
}	
			}
		}
	// stage('Docker Build & Push') {
    // 	agent any
    //   steps {
    //   	sh 'docker build -t rameshandroid99/pipeline:latest .'
	// 	sh 'docker push rameshandroid99/pipeline:latest'
    //   }
    // }
  }
}