pipeline {
  agent none
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
        sh '''docker build -f curriculum-front/Dockerfile .
'''
      }
    }

    stage('Login to docker hub') {
      agent any
      environment {
        DOCKER_USER = 'AZUNDAH'
        DOCKER_PASS = 'dondizzy12'
      }
      steps {
        sh 'docker login -u $DOCKER_USER -p $DOCKER_PASS'
      }
    }

  }
  environment {
    DOCKER_USER = 'AZUNDAH'
    DOCKER_PASS = 'dondizzy12'
  }
}