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
        echo 'Testing using Robot Framework'
        sh 'robot test_cases.robot'
      }
    }
    stage('Test suite 2. PyTest') {
      steps {
        echo 'Testing using PyTest Framework'
        sh 'python3 -m pytest test_dqchecks_sqlscripts.py'
      }
    }
     stage('Test suite 3. PyTest') {
      steps {
        sh 'python3 -m pytest test_dqchecks_methods.py'
      }
    }
     stage('Create new branch') {
      steps {
        sh 'git config --global user.name "AnastasiyaPavlovskayaT"'
        sh 'git config --global user.email "at.pavlovskaya@gmail.com"'
        sh 'git config --list'
        sh 'git checkout -b release10'
        sh 'git push https://oauth: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@github.com/AnastasiyaPavlovskayaT/ci-cd-dq-m5-test.git'
      }
    }
  }
}
