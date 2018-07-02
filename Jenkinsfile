pipeline {
  agent any
  stages {
    stage('TE1') {
      parallel {
        stage('TE1') {
          steps {
            echo 'test'
          }
        }
        stage('TE2') {
          steps {
            echo 'test2'
          }
        }
      }
    }
    stage('Cross Checking') {
      steps {
        echo 'teste3'
      }
    }
  }
}