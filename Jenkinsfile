pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t app:test .'
      }
    }
    stage('Test') {
      steps {
        echo 'TEST'
        sh 'docker run --rm --name app -id -p 80:80 app:test'
        sh '/bin/nc -vz localhost 80'
      }
      post {
          always {
              sh 'docker container stop app'
          }
      }
    }
    stage('Push Regestry') {
      steps {
        withDockerRegistry([credentialsId: "DockerHub", url: "https://index.docker.io/v1/"]) {
          sh 'docker tag app:test hperez77/app:stable'
          sh 'docker push hperez77/app:stable'
          
        }
      }
    }
  }
}
