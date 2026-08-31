pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/AmalkumarG/mern_docker.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                sh 'docker compose -p mern_docker build'
            }
        }

        stage('Deploy Application') {
            steps {
                sh 'docker compose -p mern_docker down'
                sh 'docker compose -p mern_docker up -d'
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'docker compose -p mern_docker ps'
            }
        }
    }
}
