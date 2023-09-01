pipeline {
    agent any
    
    stages {
        stage("Security Scan") {
    steps {
        echo "Performing security scan..."
        // Integrate a security scanning tool like OWASP ZAP or Nessus
    }
    post{
                success{
                    mail to : "minunsunil@gmail.com",
                    subject : "build status email",
                    body : "build was successfull"
                }
            }
}

}
}

