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
       stage('pypyodbc') {
      steps {
        sh 'pip install pypyodbc'
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
        stage('hello') {
      steps {
        sh 'python3 test_dqchecks_sqlscripts.py'
      }
    }
  }
}
