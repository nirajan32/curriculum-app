pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/nirajan32/curriculum-app.git', branch: 'dev')
      }
    }

    stage('log') {
      steps {
        sh 'ls -la'
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -f curriculum-front/Dockerfile . -t nireniru/blueocean:latest'
      }
    }

    stage('Log in to Dockerhub') {
      environment {
        DOCKERHUB_USER = 'nireniru'
        DOCKERHUB_PASSWORD = 'nirajanbhawana123@'
      }
      steps {
        sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
      }
    }

    stage('Push') {
      steps {
        sh 'docker push nireniru/blueocean:latest'
      }
    }

  }
}