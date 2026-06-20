pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE = 'docker-demo-app'
        // ИСПРАВЛЕНО: Обращаемся к переменной напрямую без ${...} и кавычек
        DOCKER_TAG   = env.BUILD_NUMBER 
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // ИСПРАВЛЕНО: Добавлена точка в конце команды, чтобы указать контекст сборки
                    sh "docker build -t ${DOCKER_IMAGE}:${DOCKER_TAG} ."
                }
            }                                                                        
        }
    }
}