pipeline {
  agent any
  stages {
    stage('Paraller execution') {
      parallel {
        stage('Say Hello') {
          steps {
            sh 'echo "Hello world"'
          }
        }

        stage('Build app') {
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