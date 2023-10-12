pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // Check out the source code from your GitHub repository
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                // Build the Docker image
                script {
                    def customImage = docker.build("my-node-app:${env.BUILD_ID}")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                // Run the Docker container
                script {
                    customImage.run("-p 8080:8080 -d")
                }
            }
        }
    }
}
