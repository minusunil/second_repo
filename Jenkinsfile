pipeline {
    agent any
    stages {
        stage('Security Scan') {
            steps {
                echo "Performing security scan..."
                // Integrate a security scanning tool like OWASP ZAP or Nessus
            }
        }
        
        post {
            always {
                def subject = currentBuild.resultIsBetterOrEqualTo('SUCCESS') ? "Security Scan Status - Success" : "Security Scan Status - Failure"
                def body = currentBuild.resultIsBetterOrEqualTo('SUCCESS') ? "Security scan passed" : "Security scan failed"
                def logFile = "${workspace}/security_scan_logs.txt"

                mail to: 'minunsunil@gmail.com',
                     subject: subject,
                     body: body,
                     attachmentsPattern: logFile
            }
        }
    }
}


