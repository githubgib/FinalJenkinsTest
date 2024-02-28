pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the repository
                git 'https://github.com/yourusername/yourrepository.git'
            }
        }
        
        stage('Linting') {
            steps {
                // Run linting checks
                sh 'flake8 .'
            }
        }
        
        stage('Build') {
            steps {
                // Add your build steps here
            }
        }
    }
    
    post {
        always {
            // Archive artifacts or perform cleanup tasks
        }
        
        success {
            // If linting and build are successful, proceed
            echo 'Linting passed! Proceeding with the build.'
        }
        
        failure {
            // If linting fails, fail the build
            echo 'Linting failed! Failing the build.'
            currentBuild.result = 'FAILED'
            error('Linting failed!')
        }
    }
}
