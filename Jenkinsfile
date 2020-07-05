pipeline {
  agent any
  stages {

   node("saltstack"){
    stage('Checkout') {
      agent any
      steps {
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
