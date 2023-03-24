pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/AXUNDA/curriculum-app', branch: 'dev')
      }
    }

    stage('log') {
      parallel {
        stage('log') {
          steps {
            sh 'ls -la'
          }
        }

        stage('unit test') {
          steps {
            sh 'cd curriculum-front && node --max-old-space-size=1000 $(which npm) install && npm i &&  npm install vue-jest && npm run test:unit'
          }
        }

      }
    }

  }
}