pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE = 'docker-demo-app'
        DOCKER_TAG   = "${env.BUILD_NUMBER}" 
    }

    stages {
		stage('Build Docker Image') {
    steps {
        script {
            // Плагин сам подхватит Docker и соберет образ
            docker.build("docker-demo-app:${env.BUILD_NUMBER}")
        }
    }
}
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t ${DOCKER_IMAGE}:${DOCKER_TAG} ."
                }
            }                                                                        
        }
    }
}