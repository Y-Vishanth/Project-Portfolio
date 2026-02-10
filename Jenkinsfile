pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/Y-Vishanth/portfolio-devops.git'
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

