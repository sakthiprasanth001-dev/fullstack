pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sakthiprasanth001-dev/fullstack.git'
            }
        }

        stage('Build Backend Image') {
            steps {
                sh 'docker build -t backend-app ./backend'
            }
        }

        stage('Run Backend') {
            steps {
                sh 'docker run -d -p 5000:5000 backend-app'
            }
        }

        stage('Build Frontend Image') {
            steps {
                sh 'docker build -t frontend-app ./frontend'
            }
        }

        stage('Run Frontend') {
            steps {
                sh 'docker run -d -p 80:80 frontend-app'
            }
        }

    }
}
