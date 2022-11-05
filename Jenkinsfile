pipeline {
  agent {
    docker {
      image 'python:3'
      label 'my-build-agent'
    }
  }
  stages {
    stage('version') {
      steps {
        sh 'python --version'
      }
    }
    stage('hello') {
      steps {
        sh 'python hello.py'
      }
    }
  }
}
