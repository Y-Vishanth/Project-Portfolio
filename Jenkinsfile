pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t portfolio-app .'
            }
        }

        stage('Deploy Portfolio') {
            steps {
                sh '''
                docker stop portfolio || true
                docker rm portfolio || true
                docker run -d --name portfolio -p 80:80 portfolio-app
                '''
            }
        }
    }
}

