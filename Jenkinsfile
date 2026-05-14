pipeline {
    agent any
    tools {
        maven 'Maven_Local'
    }
    stages {
        stage('Source Control') {
            steps {
                checkout scm
            }
        }
        stage('Build & Package') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy to Apache') {
            steps {
                // Ensure LabsKraft user has permission for /var/www/html
                sh 'cp src/main/webapp/index.html /var/www/html/'
                echo "EVALUATION_SUCCESS: CODE_DEPLOYED"
            }
        }
    }
}
