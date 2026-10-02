pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building Docker Image...'
                bat 'docker build -t nodejs-jenkins-app:latest .'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Automated Tests...'
                bat 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application container...'
                bat 'docker run -d --name test-app -p 3000:3000 nodejs-jenkins-app:latest || exit 0'
            }
        }
    }
}
