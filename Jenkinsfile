pipeline {
    agent any
    
    stages {
        stage("Security Scan") {
    steps {
        echo "Performing security scan..."
        // Integrate a security scanning tool like OWASP ZAP or Nessus
    }
    post {
        always { // This will run whether the stage succeeds or fails
            script {
                def subject = currentBuild.resultIsBetterOrEqualTo('SUCCESS') ? "Security Scan Status - Success" : "Security Scan Status - Failure"
                def body = currentBuild.resultIsBetterOrEqualTo('SUCCESS') ? "Security scan passed" : "Security scan failed"
                def logFileName = "${currentBuild.resultIsBetterOrEqualTo('SUCCESS') ? 'success' : 'failure'}_security_scan_logs.txt"

                emailext subject: subject,
                        body: body,
                        to: "minunsunil@gmail.com",
                        attachmentsPattern: "logs/$logFileName"
            }
        }
    }
}

}
}

