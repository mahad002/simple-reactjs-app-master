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
        
        stage('Run Tests') {
            steps {
                // Run tests
                bat 'npm test'
            }
        }
        
        stage('Build') {
            steps {
                // Build the project
                bat 'npm run build'
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
