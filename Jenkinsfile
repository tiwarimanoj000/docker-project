pipeline {
  agent any
  stages {
    stage ('send dockerfile to the docker server') {
      steps {
        sshagent(['docker-server']) {
          sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.13.220 '
          sh 'scp /var/lib/jenkins/workspace/docker-project/* ec2-user@172.31.13.220: /home/ec2-user'
     
        }
        }
    }
  
  }
}
