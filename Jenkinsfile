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
            sh 'cd curriculum-front &&  npm i  && npm run tests:unit'
          }
        }

      }
    }

  }
}