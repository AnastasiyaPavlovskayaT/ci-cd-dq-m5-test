pipeline {
  agent any
  stages {
        stage('version') {
      steps {
        sh 'python3 --version'
      }
    }
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
    stage('test robot run') {
      steps {
        sh 'robot test_cases.robot'
      }
    }
    stage('tests pytest 1 suite') {
      steps {
        sh 'python3 test_dqchecks_sqlscripts.py'
      }
    }
        stage('tests pytest 2 suite') {
      steps {
        sh 'python3 test_dqchecks_methods.py'
      }
    }
  }
}
