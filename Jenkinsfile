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
     stage("Build") {
            steps {
                // Create a dummy file in the repo
                sh('echo \$BUILD_NUMBER > example-\$BUILD_NUMBER.md')
            }
        }
       stage("Commit") {
            steps {
                sh('''
                    git checkout -B $TARGET_BRANCH
                    git config user.name 'AnastasiyaPavlovskayaT'
                    git config user.email 'at.pavlovskaya@gmail.com'
                    git add . && git commit -am "[Jenkins CI] Add build file"
                ''')
            }
        }
    stage("Push") {
            environment {
                GIT_AUTH = credentials('support-team-up')
            }
            steps {
                sh('''
                    git config --local credential.helper "!f() { echo username=\\$GIT_AUTH_USR; echo password=\\$GIT_AUTH_PSW; }; f"
                    git push origin HEAD:$TARGET_BRANCH
                ''')
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
