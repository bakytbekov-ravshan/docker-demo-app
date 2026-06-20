pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Скачиваем актуальный код из Git
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Используем плагин Docker Pipeline для сборки образа
                    docker.build("docker-demo-app:${env.BUILD_NUMBER}")
                }
            }
        }
    }
}