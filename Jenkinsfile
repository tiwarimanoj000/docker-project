pipeline {
  agent any
  stages {
    stage ("git checkout") {
      steps {
        sh 'git branch: 'main', changelog: false, poll: false, url: 'https://github.com/tiwarimanoj000/docker-project.git''
      
      }
    
    }
  
  }
}
