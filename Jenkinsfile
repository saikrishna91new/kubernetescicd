pipeline {
  
 agent any
  
  stages {
    stage (listWorkspace) {
      steps {
        sh 'echo ${WORKSPACE}'
       sh 'ls -ltr'   
      }
    }
    stage (builddockerimage) {
      steps {
          sh 'ssh jenkins@18.237.185.198 docker ps'
          sh 'scp -rp Dockerfile jenkins@18.237.185.198:/home/jenkins/'
          sh 'ssh jenkins@18.237.185.198 ls -ltr'
          sh 'ssh jenkins@18.237.185.198 docker build -t httpd_new .'
      }
    }
  }
}
