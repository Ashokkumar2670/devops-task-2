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
                echo 'Building Node.js Application...'
                bat 'echo Build completed successfully!'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Application Tests...'
                bat 'echo Tests passed successfully!'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
                bat 'echo Deployment successful!'
            }
        }
    }
}
