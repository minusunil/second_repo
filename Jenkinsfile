pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven..."
                // You can replace the echo command with the actual build commands
            }
            post {
                success {
                        subject: "Build Status: Success",
                        body: "The code build was successful.",
                        mail to: "minunsunil@gmail.com",
                        attachmentsPattern: '**/target/*.log'
                }
                failure {
                    emailext (
                        subject: "Build Status: Failure",
                        body: "The code build has failed. Please check the attached logs for details.",
                        to: "minunsunil@gmail.com",
                        attachmentsPattern: '**/target/*.log'
                    )
                }
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit and integration tests..."
                // You can replace the echo command with the actual test commands
            }
            post {
                success {
                    emailext (
                        subject: "Test Status: Success",
                        body: "Unit and integration tests have passed.",
                        to: "minunsunil@gmail.com",
                        attachmentsPattern: '**/target/*.log'
                    )
                }
                failure {
                    emailext (
                        subject: "Test Status: Failure",
                        body: "Unit and integration tests have failed. Please check the attached logs for details.",
                        to: "minunsunil@gmail.com",
                        attachmentsPattern: '**/target/*.log'
                    )
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo "Analyzing code for quality..."
                // You can replace the echo command with the actual code analysis commands
            }
        }
        
        stage('Security Scan') {
            steps {
                echo "Performing security scan..."
                // You can replace the echo command with the actual security scan commands
            }
            post {
                failure {
                    emailext (
                        subject: "Security Scan Status: Failure",
                        body: "Security scan has found vulnerabilities. Please take immediate action.",
                        to: "minunsunil@gmail.com"
                    )
                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo "Deploying to staging server..."
                // You can replace the echo command with the actual deployment commands
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on staging..."
                // You can replace the echo command with the actual integration test commands
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploying to production server..."
                // You can replace the echo command with the actual deployment commands
            }
        }
    }
}

