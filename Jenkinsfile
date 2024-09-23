pipeline {
  agent {
    label 'rsumangil'
  }
  stages {
    stage ('Build') {
      steps {
        sh 'docker build -t rsumangil/node-webapp:latest . '
        sh 'docker push rsumangil/node-webapp:latest '
      }
    }
    stage ('Deploy') {
      steps {
        sh 'docker run -d --name node-webapp -p 8080:8080 rsumangil/node-webapp:latest'
      }
    }
  }
}
