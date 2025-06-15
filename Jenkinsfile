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
                sh 'echo Compiling source code...'
            }
        }

        stage('Clone Target') {
            steps {
                echo '📥 Cloning second repository...'
                // Cloning another repo using shell command
                sh '''
                    rm -rf node-repo-two
                    git clone https://github.com/ashisheeSoft/node-repo-two.git
                    cd node-repo-two
                    git status
                '''
            }
        }

        stage('Test') {
            steps {
                echo '🧪 Running tests...'
                sh 'echo Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying application...'
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
