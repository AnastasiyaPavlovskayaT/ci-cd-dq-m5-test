pipeline {
  agent any
  stages {
    stage('version') {
      steps {
        sh 'python3 --version'
      }
    }
    stage('hello') {
      steps {
        sh 'python3 hello.py'
      }
   stage('robot') {
      steps {
        sh 'pip install robotframework'
      }  
    }
  }
}
