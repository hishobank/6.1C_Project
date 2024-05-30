pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project using Maven....'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests using JUnit...'
            }
            post {
                success {
                    emailext(
                        body: 'Unit and Integration Tests stage execution successful!',
                        subject: 'Unit and Integration Tests stage Success',
                        to: 'jakanraj007@gmail.com',
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        body: 'Unit and Integration Tests stage execution failed!',
                        subject: 'Unit and Integration Tests stage Failure',
                        to: 'jakanraj007@gmail.com',
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis using SonarQube...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP Dependency Check...'
            }
            post {
                success {
                    emailext(
                        body: 'Security Scan stage execution successful!',
                        subject: 'Security Scan stage Success',
                        to: 'jakanraj007@gmail.com',
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        body: 'Security Scan stage execution failed!',
                        subject: 'Security Scan stage Failure',
                        to: 'jakanraj007@gmail.com',
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server using Docker Compose...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on the staging environment...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server using Octopus Deploy...'
            }
        }
    }
}
