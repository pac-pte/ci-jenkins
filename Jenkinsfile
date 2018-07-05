import groovy.json.*
pipeline {
  agent any
  stages {
    stage('Get GQAF Variables') {
      steps {
        echo 'Getting GQAF Variables'
      }
    }
    stage('Pushing TE1') {
      parallel {
        stage('TE1') {
          steps {
            //build 'TE1/RTPMC_System/0010.LIVEBOOK_UBS-Headline'
            echo 'TE1'
          }
        }
        stage('TE2') {
          when{
                expression { 'official' == 'notofficial' } 
            }
          steps {
            //build 'TE2/RTPMC_System/0010.LIVEBOOK_UBS-Headline'
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
        when{
                expression { 'official' == 'notofficial' } 
            }
          steps {
            echo 'Set Reference'
          }
    }
    
    stage('Trigger 2 DEBUG JOBS') {
      parallel {
        stage('HEAD DEBUG') {
          steps {
            //build 'TE1/RTPMC_System/0010.LIVEBOOK_UBS-Headline'
            echo 'PUSH HEAD DEBUG'
          }
        }
        stage('REF DEBUG') {
          
          steps {
            //build 'TE2/RTPMC_System/0010.LIVEBOOK_UBS-Headline'
             echo 'PUSH REF DEBUG'
          }
        }
      }
    }
     stage('SEND MAIL') {
          
          steps {
            //build 'TE2/RTPMC_System/0010.LIVEBOOK_UBS-Headline'
             echo 'Sending Mail'
          }
    }
    
  }
}
