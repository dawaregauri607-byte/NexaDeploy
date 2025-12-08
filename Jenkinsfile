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
    }
}
