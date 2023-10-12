pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    def dockerImage = docker.build("my-docker-image:latest", ".")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    def containerId = dockerImage.run('-p 8080:80 -d')
                }
            }
        }
    }
}
