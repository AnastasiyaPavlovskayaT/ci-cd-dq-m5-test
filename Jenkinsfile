pipeline {
  agent any
  stages {
    stage('version') {
      steps {
        sh 'pip install robotframework'
      }
    }
    stage('hello') {
      steps {
        sh 'python3 hello.py'
      }
    }
  }
}
