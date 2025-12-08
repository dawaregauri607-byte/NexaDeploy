pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/dawaregauri607-byte/NexaDeploy.git'
            }
        }
        stage('Build API') {
            steps {
                sh 'cd api && npm install'
            }
        }
        stage('Build UI') {
            steps {
                echo 'UI Ready'
            }
        }
    }
}
