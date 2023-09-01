pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Build automation tool: Maven"
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo "Unit test automation tool: JUnit"
                echo "Integration test automation tool: TestNG"
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo "Code analysis tool: SonarQube"
            }
        }
        
        stage('Security Scan') {
            steps {
                echo "Security scanning tool: OWASP ZAP"
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo "Deployment tool: AWS CodeDeploy"
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo "Integration test automation tool: TestNG"
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deployment tool: AWS CodeDeploy"
            }
        }
    }
    
    post {
        always {
            archiveArtifacts artifacts: '**/target/*.log', allowEmptyArchive: true
            script {
                def subject = "Pipeline ${currentBuild.result}: ${currentBuild.fullDisplayName}"
                def body = "The pipeline has ${currentBuild.result}."
                emailext (
                    subject: subject,
                    body: body,
                    attachmentsPattern: '**/target/*.log',
                    to: 'your-email@example.com'
                )
            }
        }
    }
}
