pipeline {
    agent any

    stages {
        stage('Build') {
        steps {
            echo 'Checking Python syntax...'
            bat '"C:\\Users\\anish\\AppData\\Local\\Python\\bin\\python.exe" -m py_compile app.py test_app.py'
        }
}

        stage('Test') {
        steps {
            echo 'Running application tests...'
            bat '"C:\\Users\\anish\\AppData\\Local\\Python\\bin\\python.exe" test_app.py'
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