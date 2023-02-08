pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/nirajan32/curriculum-app.git', branch: 'dev')
      }
    }

    stage('log') {
      parallel {
        stage('log') {
          steps {
            sh 'ls -la'
          }
        }

        stage('Front-End Unit Tests') {
          steps {
            sh 'cd curriculum-front && npm i && npm run test:unit'
          }
        }

      }
    }

  }
}