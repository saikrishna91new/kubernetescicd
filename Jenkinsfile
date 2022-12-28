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
    stage('Build'){
  steps{
  sh  "mvn clean package"
  }
  }
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
        sh 'scp -o StrictHostKeyChecking=no deployment.yaml jenkins@172.31.15.191:/root/'
        sh 'ssh jenkins@172.31.15.191 kubectl get deployments'
  }
}
  }
}
