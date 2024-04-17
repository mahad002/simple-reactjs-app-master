pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git branch: 'main', url:'https://github.com/mahad002/simple-reactjs-app-master'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                bat 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                // Build the project
                bat 'npm run build'
            }
        }
        
        stage('Docker Build') {
            steps {
                // Build Docker image
                bat 'docker build -t simple-reactjs-app-master .'
            }
        }
    }
    
    post {
        success {
            // If the build is successful, archive the build artifacts
            archiveArtifacts artifacts: 'build/**'
        }
    }
}
