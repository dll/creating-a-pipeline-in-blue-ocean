pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'npm install'
      }
    }

    stage('Test') {
      agent any
      environment {
        CI = 'true'
      }
      steps {
        bat 'npm test'
      }
    }

    stage('Delivery') {
      steps {
        bat 'npm run build'
      }
    }

    stage('Run') {
      steps {
        bat 'npm start & sleep 1 echo $! > .pidfile'
      }
    }

  }
}