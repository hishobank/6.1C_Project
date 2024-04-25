pipeline {
    agent any
    
    environment {
        DIRECTORY_PATH = "D:\\AI\\Sem 2\\SIT753\\Ontrack"
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Compile the code, and create any artifacts that are required."
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo "Run unit tests."
                echo "Implementation tests."
            }
            post {
                success {
                    emailext body: 'Unit and Integration Tests stage execution successful!',
                             subject: 'Unit and Integration Tests stage Success',
                             to: 'khishoban@gmail.com',
                             attachLog: true
                }
                failure {
                    emailext body: 'Unit and Integration Tests stage execution failed!',
                             subject: 'Unit and Integration Tests stage Failure',
                             to: 'khishoban@gmail.com',
                             attachLog: true
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo "Check the quality of the code."
            }
        }
        
        stage('Security Scan') {
            steps {
                echo "Performing a security scan on the code"
            }
            post {
                success {
                    emailext body: 'Security Scan stage execution successful!',
                             subject: 'Security Scan stage Success',
                             to: 'khishoban@gmail.com',
                             attachLog: true
                }
                failure {
                    emailext body: 'Security Scan stage execution failed!',
                             subject: 'Security Scan stage Failure',
                             to: 'khishoban@gmail.com',
                             attachLog: true
                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to a staging server"
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo "Run integration tests"
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploy the code to the production environment"
            }
        }
    }
    
    post {
        success {
            echo "Pipeline execution successful!"
        }
        failure {
            echo "Pipeline execution failed!"
            emailext body: 'Pipeline execution failed. Please check the logs for details.',
                     subject: 'Pipeline Failure',
                     to: 'khishoban@email.com',
                     attachLog: true
        }
    }
}
