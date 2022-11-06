pipeline {
  agent any
  stages {
    stage('robot') {
      steps {
        sh 'pip install robotframework'
      }
    }
   stage('robotdb') {
      steps {
        sh 'pip install robotframework-databaselibrary'
      }
    }
   stage('pymssql') {
      steps {
        sh 'pip install pymssql'
      }
    }
    stage('hello') {
      steps {
        sh 'python3 hello.py'
      }
    }
    stage('test robot run') {
      steps {
        sh 'robot test_cases.robot'
      }
    }
  }
}
