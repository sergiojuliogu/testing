pipeline {
  agent {
    docker {
      image 'doker:latest'
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