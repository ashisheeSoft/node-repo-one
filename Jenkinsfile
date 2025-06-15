pipeline {
    agent any

    environment {
        // Define environment variables if needed
        APP_ENV = 'development'
    }

    stages {
        stage('Build') {
            steps {
                echo '🔨 Building the application...'
                // Example: compile code
                sh 'echo Compiling source code...'
            }
        }

        stage('Test') {
            steps {
                echo '🧪 Running tests...'
                // Example: run unit tests
                sh 'echo Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying application...'
                // Example: copy files or run deployment script
                sh 'echo Deploying to dev environment...'
            }
        }
    }

    post {
        always {
            echo '📦 Pipeline finished.'
        }
        success {
            echo '✅ Build succeeded!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
