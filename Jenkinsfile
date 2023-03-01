pipeline {
  agent {
    docker {
      image 'node:lts-alpine'
      args '-p 3000:3000 '
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh 'npm test '
      }
    }

    stage('Deliver') {
      steps {
        sh '''npm start &
sleep 1'''
        input '"Terminar"'
        sh 'kill $(cat .pidfile)'
      }
    }

  }
}