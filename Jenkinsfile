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
      steps {
        sh '"docker build -t lordagam/node-hello-new:${\'env.BUILD_NUMBER\'} ."'
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