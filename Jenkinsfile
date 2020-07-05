pipeline {
  agent any
  stages {

   agent any
   node("saltstack"){
    stage('Checkout') {
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
