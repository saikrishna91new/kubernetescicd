pipeline {
  
  agent {
    node {
      label 'workernode'
    }
  }
   options {
     timestamps()
     buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5'))
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
          sh 'docker build -t httpd_new .'
      }
    }
    stage (deployToKuberentesMaster) {
      steps {
        when {
          brnach 'master'
        }
        sh 'scp -rp deployment.yaml jenkins@172.31.15.191:
  }
}
