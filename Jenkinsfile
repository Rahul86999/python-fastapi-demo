pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Rahul86999/python-fastapi-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t fastapi-app .'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'docker run --rm fastapi-app pytest'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
