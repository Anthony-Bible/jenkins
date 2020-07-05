pipeline {
  agent any
  stages {
    stage('Checkout') {
      agent any
      steps {
        node{
        git 'https://github.com/Anthony-Bible/Cluster.git'
        dir(path: './cluster') {
          git 'https://github.com/Anthony-Bible/Registration.git'
          script {
            docker.build registry + ":$BUILD_NUMBER"
          }

        }

      }
     }
    }

  }
  environment {
    registry = 'gimpyb/mystaticsite-container-prod'
    registryCredential = 'dockerhub'
  }
}
