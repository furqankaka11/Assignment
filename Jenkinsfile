pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/furqankaka11/assignment.git'
            }
        }
        stage('Build and Run Docker Compose') {
            steps {
                sh 'docker-compose build'
                sh 'docker-compose up -d'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'docker-compose run --rm fullstack-app pytest'
            }
        }
        stage('Push Docker Image to Docker Hub') {
            steps {
                sh 'docker login --username=$DOCKER_HUB_USERNAME --password=$DOCKER_HUB_PASSWORD'
                sh 'docker tag fullstack-app:latest $DOCKER_HUB_USERNAME/fullstack-app:$BUILD_NUMBER'
                sh 'docker push $DOCKER_HUB_USERNAME/fullstack-app:$BUILD_NUMBER'
            }
        }
    }
}
