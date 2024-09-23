pipeline {
  agent {
    label 'rsumangil'
  }
  stages {
    node {

      checkout scm
      def dockerImage

      stage('Build image') {
        dockerImage = docker.build("username/repository:tag")
      }

      stage('Push image') {
        dockerImage.push()
      }   

    }
    stage ('Deploy') {
      steps {
        sh 'docker run -d --name node-webapp -p 8080:8080 my-image'
      }
    }
  }
}
