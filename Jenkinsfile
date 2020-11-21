pipeline {
  agent any
  environment{
      DOCKER_USER=credentials('DOCKER_USER')
      DOCKER_PASSWORD=credentials('DOCKER_PASSWORD')
  }
  stages {
      stage('get repo') {
        steps {
            sh 'chmod a+x ./scripts/get-repo.sh'
            sh './scripts/get-repo.sh'
        }
      }
    stage('docker login') {
        steps {
          sh 'docker login --username=${DOCKER_USER} --password=${DOCKER_PASSWORD}'
        }
      }
   }
}


