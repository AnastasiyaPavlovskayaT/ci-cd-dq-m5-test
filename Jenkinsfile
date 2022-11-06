pipeline {
  agent {
    docker {
        //This image parameter (of the agent section’s docker parameter) downloads the python:2-alpine
        //Docker image and runs this image as a separate container. The Python container becomes
        //the agent that Jenkins uses to run the Build stage of your Pipeline project.
        image 'python:2-alpine'
    }
  }
  stages {
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
