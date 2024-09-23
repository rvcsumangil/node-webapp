pipeline {
  agent {
    label 'rsumangil'
  }
  stages {
    stage ('Build') {
      steps {
        sh 'cd /home/rsumangil/node-webapp'
        sh 'docker build -t rsumangil/node-webapp:latest . '
        sh 'docker push rsumangil:5000/node-webapp:latest '
      }
    }
    stage ('Deploy') {
      steps {
        sh 'docker run -d --name node-webapp -p 8080:8080 rsumangil:5000/node-webapp:latest'
      }
    }
  }
}
