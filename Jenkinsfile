pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Surya3112-cloud/s3-github.git'
            }
        }

        stage('Verify Files') {
            steps {
                sh 'echo "Listing website files..."'
                sh 'ls -la'
            }
        }

        stage('Deploy Website') {
            steps {
                sh '''
                echo "Deploying static website..."
                cp -r * /var/www/html/
                '''
            }
        }
    }

    post {
        success {
            echo 'Website deployed successfully!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
