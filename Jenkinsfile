pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      parallel {
        stage('Static code analysis') {
          steps {
            sh 'npm run test'
          }
        }

        stage('Unit tests') {
          steps {
            sh 'npm run test'
          }
        }

      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }

  }
}