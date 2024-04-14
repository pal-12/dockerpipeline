pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
git branch: 'main', url: 'https://github.com/pal-12/dockerpipeline'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
sh 'docker build -t docker-pipe-line https://github.com/pal-12/dockerpipeline '
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh 'docker run -d --docker-pipe-line -p 8090:8090 docker-pipe-line'
                }
            }
        }
    }
}
