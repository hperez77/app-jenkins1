pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'BUILD'
        echo ''
      }   
    }
    stage('Test') {
      steps {
        echo 'TEST'
      }
    }
    stage('Deploy') {
      steps {
        echo 'DEPLOY'
      }
    }
    post {
      always(dir){
        cleanWS
      }
    }
  }
}
