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
        sh '''docker build -f curriculum-front/Dockerfile .
'''
      }
    }

  }
}