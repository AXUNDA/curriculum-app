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

        stage('fron end test') {
          steps {
            sh 'cd curriculum-front && node --max-old-space-size=1000000 $(which npm) install && npm install  && npm run tests:unit'
          }
        }

      }
    }

  }
}