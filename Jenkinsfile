pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/dawaregauri607-byte/NexaDeploy.git'
            }
        }

        stage('Build API') {
            steps {
                bat 'cd api && npm install'
            }
        }

        stage('Build UI') {
            steps {
                bat 'cd ui && npm install'
            }
        }

        stage('Build API Docker Image') {
            steps {
                bat 'docker build -t nexa-api:latest ./api'
            }
        }

        stage('Build UI Docker Image') {
            steps {
                bat 'docker build -t nexa-ui:latest ./ui'
            }
        }

        stage('Login to DockerHub') {
            steps {
                bat 'docker login -u dawaregauri607 -p YOUR_DOCKER_PASSWORD'
            }
        }

        stage('Push API Image to DockerHub') {
            steps {
                bat 'docker tag nexa-api:latest dawaregauri607/nexa-api:latest'
                bat 'docker push dawaregauri607/nexa-api:latest'
            }
        }

        stage('Push UI Image to DockerHub') {
            steps {
                bat 'docker tag nexa-ui:latest dawaregauri607/nexa-ui:latest'
                bat 'docker push dawaregauri607/nexa-ui:latest'
            }
        }
    }
}
