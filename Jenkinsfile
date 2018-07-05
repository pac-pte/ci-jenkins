pipeline {
  agent any
  stages {
    stage('Get GQAF Variables') {
      steps {
        echo 'Getting GQAF Variables'
      }
    }
    stage('Pushing TE1 & TE2') {
      parallel {
        stage('TE1') {
          steps {
            echo 'TE1'
          }
        }
        stage('TE2') {
          when {
            expression {
              'official' == 'notofficial'
            }

          }
          steps {
            echo 'TE2'
          }
        }
      }
    }
    stage('Cross Checking') {
      steps {
        echo 'Cross Checking'
      }
    }
    stage('Set Reference') {
      when {
        expression {
          'official' == 'notofficial'
        }

      }
      steps {
        echo 'Set Reference'
      }
    }
    stage('Trigger 2 DEBUG JOBS') {
      parallel {
        stage('HEAD DEBUG') {
          steps {
            echo 'PUSH HEAD DEBUG'
          }
        }
        stage('REF DEBUG') {
          steps {
            echo 'PUSH REF DEBUG'
          }
        }
      }
    }
    stage('SEND MAIL') {
      steps {
        echo 'Sending Mail'
      }
    }
  }
}