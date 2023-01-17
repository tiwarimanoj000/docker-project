pipeline {
  agent any
  stages {
    stage ('send dockerfile to the docker server') {
      steps {
        sshagent(['docker-server']) {
          sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.13.220'
          sh 'scp /var/lib/jenkins/workspace/docker-project/* ec2-user@172.31.13.220:/home/ec2-user/'
          
     
        }
        }
    }
    stage ('build the docker file and push to the docker hub') {
      steps {
          sshagent(['docker-server']) {
          sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.13.220 cd /home/ec2-user/'
            sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.13.220 docker build -t myimage:2.0 .'
          }
      
      }
    
    }
    stage ('docker login and push to the docker hub') {
      steps {
        sshagent(['docker-server']) {
          withCredentials([string(credentialsId: 'dockerpwd', variable: 'dockerpwd')]) {
             sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.13.220 docker login -u manojtiwari000 -p ${dockerpwd}'
            sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.13.220 docker image push myimage:2.0'
            
            }
        
        }
      
      }
    
    }
  
  }
}
