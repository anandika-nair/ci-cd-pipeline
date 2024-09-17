pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building the project."
            }
        }
    }
}
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing Code Analysis...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing Security Scan...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
            }
        }
    }
}
post {
    always {
        mail to: 'anandikarajeevnair@gmail.com',
             subject: "Pipeline Result: ${currentBuild.fullDisplayName}",
             body: "The pipeline finished with status: ${currentBuild.currentResult}"
    }
}
