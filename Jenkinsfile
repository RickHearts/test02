pipeline {
  agent any
  stages {
    stage('Browsers') {
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

    stage('Edge') {
      steps {
        input 'Do you want to continue?'
        sleep 5
        echo 'Edge Tests'
      }
    }

  }
}