pipeline {
    agent any

    stages {

        stage('Build Backend Image') {
            steps {
                sh 'docker build -t mohanbabu66/backend:v1 ./backend'
            }
        }

        stage('Build Frontend Image') {
            steps {
                sh 'docker build -t mohanbabu66/frontend:v1 ./frontend'
            }
        }

        stage('Push Backend Image') {
            steps {
                sh 'docker push mohanbabu66/backend:v1'
            }
        }

        stage('Push Frontend Image') {
            steps {
                sh 'docker push mohanbabu66/frontend:v1'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/'
            }
        }
    }
}
