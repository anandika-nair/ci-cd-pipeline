pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running static code analysis...'
                
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                
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
                to: "anandikarajeevnair@gmail.com",
                attachLog: true // Attach the console log in case of success
            )
        }
        failure {
            echo 'Pipeline failed.'
            emailext (
                subject: "Jenkins Build Failed",
                body: "The Jenkins build failed. Please check the attached build log for more details.",
                to: "anandikarajeevnair@gmail.com",
                attachLog: true // Attach the console log in case of failure
            )
        }
    }
}
