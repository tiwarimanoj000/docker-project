pipeline {
  agent any
  stages {
    stage ('send dockerfile to the docker server') {
      steps {
        sshagent(['docker-server']) {
          pwd()
        }
        }
    }
  
  }
}
