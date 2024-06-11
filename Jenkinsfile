pipeline {
    agent any
    environment {
        DOCKER_HUB_USERNAME = credentials('docker_hub').username
        DOCKER_HUB_PASSWORD = credentials('docker_hub').password
    }
    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building..."
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo "Testing..."
                }
            }
        }
        stage('Build Docker') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker_hub', url: 'https://index.docker.io/v1/') {
                        sh 'docker build -t thuhien2105/blog:blog .'
                        sh 'docker push thuhien2105/blog:blog'
                    }
                }
            }
        }
    }
}
