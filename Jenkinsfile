pipeline {
  agent {
    docker {
      image 'node:alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'npm install'
          }
        }
        stage('test') {
          steps {
            sh 'npm test'
          }
        }
        stage('deliver') {
          steps {
            sh '''id
pwd
printenv
npm start'''
          }
        }
      }
    }
  }
}