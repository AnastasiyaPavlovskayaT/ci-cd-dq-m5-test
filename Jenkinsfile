pipeline {
  agent any
  stages {
    stage('python') {
      steps {
        sh 'where python'
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
