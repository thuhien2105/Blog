pipeline {
    agent any
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
        stage('Deploy') {
            steps {
                script {
                    echo "Deploying..."
                }
            }
        }
    }
}
