pipeline {
  agent any
  stages {
    stage('Chrome') {
      parallel {
        stage('Chrome') {
          agent any
          steps {
            echo 'Chrome Tests'
          }
        }

        stage('Firefox') {
          steps {
            echo 'Firefox Tests'
          }
        }

      }
    }

  }
}