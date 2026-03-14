pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/YOUR_USERNAME/devops-cicd-jenkins-docker.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-devops-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker stop cicd-container || true
                docker rm cicd-container || true
                docker run -d -p 5000:5000 --name cicd-container cicd-devops-app
                '''
            }
        }

    }
}
