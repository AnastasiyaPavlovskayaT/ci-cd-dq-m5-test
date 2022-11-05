pipeline {
  agent any
  stages {
    stage('python') {
      steps {
        sh 'apt install python3 -y'
      }
    }
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
