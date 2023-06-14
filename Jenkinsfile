pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/lidorg-dev/hello-world-python.git', branch: 'master')
      }
    }

    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh '"docker build -t lordagam/hello-world-python:${env.BUILD_NUMBER} ."'
          }
        }

        stage('') {
          steps {
            sh '"docker run -itd --name hello-world-python -p 8080:8080 lordagam/hello-world-python:${env.BUILD_NUMBER}"'
          }
        }

        stage('stop') {
          steps {
            sh '''"docker stop hello-world-python && docker rm hello-world-python"

'''
          }
        }

      }
    }

    stage('Test') {
      steps {
        sleep 5
      }
    }

    stage('push to dockerhub') {
      steps {
        sleep 5
      }
    }

  }
}