pipeline {
    agent any

    tools {nodejs "node"}

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                 def customImage = docker.build('yogeshchaudhary/test')
                 docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                 customImage.push("${env.BUILD_NUMBER}")
                 }
               }
            }
        }
    }
}
