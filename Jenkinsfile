pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git 'https://github.com/shindenikhil659/-CI-CD-pipeline.git'
            }
        }
        
        stage('Build') {
            steps {
                // Build the Maven project
                sh 'mvn clean install'
            }
        }
        
        stage('Test') {
            steps {
                // Run Selenium tests
                sh 'mvn test'
            }
        }
        
        stage('Deploy') {
            steps {
                // Example deployment step (modify as needed)
                sh 'mvn deploy'
            }
        }
    }
    
    post {
        success {
            // Send notification on success
            emailext(
                to: 'shindenikhil659@gmail.com',
                subject: 'CI/CD Pipeline Successful',
                body: 'Your CI/CD pipeline has completed successfully.'
            )
        }
        failure {
            // Send notification on failure
            emailext(
                to: 'shindenikhil659@gmail.com',
                subject: 'CI/CD Pipeline Failed',
                body: 'Your CI/CD pipeline has failed.'
            )
        }
    }
}
