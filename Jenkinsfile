pipeline {
  agent any
  stages {
    stage('Checkout') {
      agent any
      steps {
        node(label: 'saltstack') {
          git 'https://github.com/Anthony-Bible/Cluster.git'
          dir(path: './registration') {
            git 'https://github.com/Anthony-Bible/Registration.git'
          }

          script {
            docker.build registry + ":$BUILD_NUMBER"
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