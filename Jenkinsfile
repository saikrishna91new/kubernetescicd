pipeline {
  
  agent {
    node {
      label 'workernode'
    }
  }
  
  stages {
    stage (listWorkspace) {
      steps {
        sh 'echo ${WORKSPACE}'
       sh 'ls -ltr'   
      }
    }
    stage (builddockerimage) {
      steps {
          
          sh 'ls -ltr'
      }
    }
  }
}
