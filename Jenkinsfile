pipeline {
  agent none
  stages {
    stage('Build & Test') {
      agent {
        node {
          label 'ubuntu_slave1'
        }

      }
      steps {
        sh 'mvn -Dmaven.test.failure.ignore clean package'
        stash(name: 'build-test-artifacts', includes: '**/target/surefire-reports/TEST-*.xml,target/*.jar')
      }
    }

    stage('Report & Publish') {
      parallel {
        stage('Report & Publish') {
          agent {
            node {
              label 'ubuntu_slave1'
            }

          }
          steps {
            unstash 'build-test-artifacts'
            junit '**/target/surefire-reports/TEST-*.xml'
            archiveArtifacts(artifacts: 'target/*.jar', onlyIfSuccessful: true)
          }
        }

        stage('Publishing') {
          agent {
            node {
              label 'ubuntu_slave1'
            }

          }
          steps {
            echo 'Working...'
          }
        }

      }
    }

  }
}