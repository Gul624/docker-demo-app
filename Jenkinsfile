pipeline{
    agent any
     environment {
        DOCKER_IMAGE = 'docker-demo-app'
        DOCKER_TAG = '${env.BUILD_NUMBER}'
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
                script {
                   docker.build("${DOCKER_IMAGE}:${DOCKER_TAG}")
                }
            }
        }
        
    }
}