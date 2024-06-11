pipeline {
    agent any
    environment {
        // Sử dụng withCredentials để truy cập thông tin username và password từ credentials
        DOCKER_HUB_CREDENTIALS = credentials('docker_hub')
        DOCKER_HUB_USERNAME = DOCKER_HUB_CREDENTIALS.username
        DOCKER_HUB_PASSWORD = DOCKER_HUB_CREDENTIALS.password
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
                    withDockerRegistry(url: 'https://index.docker.io/v1/', credentialsId: 'docker_hub') {
                        sh 'docker build -t thuhien2105/blog:blog .'
                        sh 'docker push thuhien2105/blog:blog'
                    }
                }
            }
        }
    }
}
