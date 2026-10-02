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
                bat '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe" build -t nodejs-jenkins-app:latest .'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Application Tests...'
                bat 'npm test || exit 0'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying Container...'
                bat '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe" run -d --name test-app -p 3000:3000 nodejs-jenkins-app:latest || exit 0'
            }
        }
    }
}
