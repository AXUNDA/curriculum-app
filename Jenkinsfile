pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/AXUNDA/curriculum-app', branch: 'dev')
      }
    }

    stage('log') {
      steps {
        sh 'ls -la'
      }
    }

    stage('front-end build') {
      steps {
        sh 'docker build -f curriculum-front/Dockerfile . '
      }
    }

    stage('Login to docker hub') {
      agent any
      environment {
        DOCKER_USER = 'azundah'
        DOCKER_PASS = 'dondizzy12'
      }
      steps {
        sh 'docker login -u $DOCKER_USER --password $DOCKER_PASS'
      }
    }

    stage('push') {
      steps {
        sh 'docker push azundah/curriculum-front:latest'
      }
    }

  }
  environment {
    DOCKER_USER = 'azundah'
    DOCKER_PASS = 'dondizzy12'
  }
}