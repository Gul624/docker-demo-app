pipeline {
    agent {
        any {
            args '-u root' // Это даст Jenkins права root внутри контейнера, и сокет прочитается
        }
    }
    environment {
        DOCKER_IMAGE = 'docker-demo-app'
        DOCKER_TAG = "${env.BUILD_NUMBER}"
    }
    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout scm
                }
            }
        }
        stage('Build Docker Image') {
            steps {
                sh "docker build -t ${DOCKER_IMAGE}:${DOCKER_TAG} ."
            }
        }
    }
}