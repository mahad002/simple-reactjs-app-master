pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git 'https://github.com/mahad002/simple-reactjs-app-master.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }
        
        stage('Run Tests') {
            steps {
                // Run tests
                sh 'npm test'
            }
        }
        
        stage('Build') {
            steps {
                // Build the project
                sh 'npm run build'
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
