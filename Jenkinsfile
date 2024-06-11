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
        stage('Test') {
            steps {
               
                    withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                        sh 'docker build -t thuhien2105/blog:blog'
                        sh 'docker push thuhien2105/blog:blog'

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
