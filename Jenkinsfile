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
       stage('pyodbc') {
      steps {
        sh 'pip install pyodbc'
      }
    }
           stage('pytest') {
      steps {
        sh 'pip install pytest'
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
    stage('tests pytest 1') {
      steps {
        sh 'python3 test_dqchecks_sqlscripts.py'
      }
    }
  }
}
