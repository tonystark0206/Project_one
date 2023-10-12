pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your GitHub repository
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Define the Docker image name and tag
                    def dockerImage = docker.build('my-node-app:latest', '.')
                }
            }
        }

        stage('Run Docker Container Locally') {
            steps {
                script {
                    // Run the Docker container locally
                    def containerId = dockerImage.run('-p 8080:8080 -d')
                }
            }
        }
    }

    post {
        success {
            // Publish an artifact, send notifications, or perform other post-build actions
        }
    }
}
