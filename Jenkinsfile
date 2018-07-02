pipeline {
  agent any
  stages {
    stage('TE1') {
      parallel {
        stage('TE1') {
          steps {
            build(job: 'Ralph Test', wait: true)
          }
        }
        stage('TE2') {
          steps {
            build(job: 'TEST', wait: true)
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