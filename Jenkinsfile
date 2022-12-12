pipeline {
  
 agent any
  
  stages {
    stage (listWorkspace) {
      steps {
       sh 'pwd'
       sh 'ls -ltr'   
      }
    }
    stage (builddockerimage) {
      steps {
          sh 'ssh jenkins@18.237.185.198 docker ps'
          sh 'ssh jenkins@18.237.185.198 docker build -t httpd_new .'
      }
    }
  }
}
