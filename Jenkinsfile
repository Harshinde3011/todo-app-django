pipeline {
    agent any
    stages {

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image using Dockerfile in the cloned repository
                    docker.build('mywebsite:latest', '.')
                }
            }
        }
        
        stage('Run Container') {
            steps {
                script {
                    // Run the Docker container from the built image
                    docker.image('mywebsite:latest').run('-p 8000:8000 -d --name webcontainer')
                }
            }
        }
    }
}
