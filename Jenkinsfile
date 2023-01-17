pipeline {
  agent any
  stages {
    stage ('send dockerfile to the docker server') {
      steps {
        sshagent(['docker-server']) {
          sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.13.220 pwd() '
          sh 'pwd'
        }
        }
    }
  
  }
}
