pipeline {
  agent any
  stages {
    stage('Installing required libraries') {
      steps {
        echo 'Installing required pyhon libraries'
        sh 'pip install robotframework'
        sh 'pip install robotframework-databaselibrary'
        sh 'pip install pymssql'
        sh 'pip install pyodbc'
        sh 'pip install pytest'
      }
    }         
    stage('Test suite 1. Robot') {
      steps {
        sh 'robot test_cases.robot'
      }
    }
    stage('Test suite 2. Pytest') {
      steps {
        sh 'python3 -m pytest test_dqchecks_sqlscripts.py'
      }
    }
     stage('Test suite 3. Pytest') {
      steps {
        sh 'python3 -m pytest test_dqchecks_methods.py'
      }
    }
  }
}
