pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'npm i'
      }
    }

    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }

  }
  environment {
    CI = ''
  }
}