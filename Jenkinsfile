pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/Anthony-Bible/Cluster.git'
        dir(path: './cluster') {
          git 'https://github.com/Anthony-Bible/Registration.git'
        }

      }
    }

  }
}