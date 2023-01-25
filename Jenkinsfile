pipeline {
  agent any
  stages {
    stage('Say hello') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo "Hello world"'
          }
        }

        stage('Say Hello') {
          agent {
            docker {
              image 'gradle:6-jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

  }
}