pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
                bat 'python -m py_compile app.py test_app.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application...'
                bat 'python test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat 'if not exist deployed mkdir deployed'
                bat 'copy /Y app.py deployed\\app.py'
                echo 'Deployment successful!'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }
        failure {
            echo 'CI/CD Pipeline failed!'
        }
    }
}