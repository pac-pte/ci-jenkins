pipeline {
  agent any
  stages {
    stage('TE1') {
      parallel {
        stage('TE1') {
          steps {
            build 'LIVEBOOK_UBS - v3.1.build'
          }
        }
        stage('TE2') {
          steps {
            build 'HEAD_2/job/RTPMC_System/job/0010.LIVEBOOK_UBS-Headline/'
          }
        }
      }
    }
    stage('Cross Checking') {
      steps {
        echo 'test'
      }
    }
  }
}