pipeline {
  agent {
    kubernetes {
      idleMinutes 5  // how long the pod will live after no jobs have run on it
      yamlFile 'build-pod.yaml'  // path to the pod definition relative to the root of our project 
      defaultContainer 'docker'  // define a default container if more than a few stages use it, will default to jnlp container
    }
  }
  stages {
    stage('Show Docker version') {
      steps {
        container('docker') {  
          sh "docker version"
        }
      }
    }
  }
}
