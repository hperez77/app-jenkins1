pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'BUILD'
        echo ''
      }
      post {
        always {
          echo 'Esto siempre saldrá por pantalla'
        }
        failure {
          
        }
        success{
        
        }
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
