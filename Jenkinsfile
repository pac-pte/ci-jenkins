pipeline {
  agent any
  stages {
    stage('TE1') {
      parallel {
        stage('TE1') {
          steps {
            build(job: '/HEAD_1/job/RTPMC_System/job/0010.LIVEBOOK_UBS-Headline', wait: true)
          }
        }
        stage('TE2') {
          steps {
            build(job: '/HEAD_2/job/RTPMC_System/job/0010.LIVEBOOK_UBS-Headline', wait: true)
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