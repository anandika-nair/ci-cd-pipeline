pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Example: For Java projects, use Maven
                // sh 'mvn clean install'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Example for Python: pytest or Java: Maven test
                // sh 'pytest'
                // sh 'mvn test'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running static code analysis...'
                // Example: SonarQube for static analysis
                // sh 'sonar-scanner'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Example: Use Snyk or OWASP ZAP
                // sh 'snyk test'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                // Example: SCP or other deployment tool
                // sh 'scp target/myapp.jar user@staging-server:/path/to/deploy'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                // Example: SCP or any deployment tool for production
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Pipeline succeeded.'
            emailext (
                subject: "Jenkins Build Successful",
                body: "The Jenkins build completed successfully.\n\nCheck the attached build log for more details.",
                to: "anandikarnair@gmail.com",
                attachLog: true // Attach the console log in case of success
            )
        }
        failure {
            echo 'Pipeline failed.'
            emailext (
                subject: "Jenkins Build Failed",
                body: "The Jenkins build failed. Please check the attached build log for more details.",
                to: "anandikarnair@gmail.com",
                attachLog: true // Attach the console log in case of failure
            )
        }
    }
}
