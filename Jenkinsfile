pipeline {
  agent {
    kubernetes {
      label 'test-app'
      idleMinutes 5
      yamlFile 'build-pod.yaml'
      defaultContainer 'maven'
      runAsUser 0
    }
  }
  stages {
    stage('Build') {
      steps {  // no container directive is needed as the maven container is the default
        sh 'mvn clean package'
      }
    }
    // stage('Build Docker Image') {
    //   steps {
    //     container('docker') {  
    //       sh 'docker build -t promo-app:dev .'
    //     }
    //   }
    // }
  }
}