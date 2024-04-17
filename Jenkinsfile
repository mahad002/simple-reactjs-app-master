pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git branch: 'main', url:'https://github.com/mahad002/simple-reactjs-app-master'
            }
        }
        
        stage('Dependency Installation') {
            steps {
                // Install Node.js dependencies
                bat 'npm install'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                // Build Docker image
                bat 'docker build -t simple-reactjs-app-master .'
            }
        }
        
        stage('Run Docker Image') {
            steps {
                // Run Docker image
                bat 'docker run -p 3000:3000 simple-reactjs-app-master'
            }
        }
        
        stage('Push Docker Image') {
            steps {
                // Push Docker image to Docker Hub
                bat 'docker push simple-reactjs-app-master'
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
