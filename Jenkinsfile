pipeline {
  agent {
    label 'rsumangil'
  }
  stages {
    stage ('Build') {
      steps {
        node {
          checkout scm
          def customImage = docker.build("my-image")
          customImage.push()
        }
      }
    }
    stage ('Deploy') {
      steps {
        sh 'docker run -d --name node-webapp -p 8080:8080 my-image'
      }
    }
  }
}
