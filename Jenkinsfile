pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/your-username/welcome-project.git'
            }
        }

        stage('Verify Files') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                sudo cp index.html /var/www/html/
                sudo cp style.css /var/www/html/
                sudo cp script.js /var/www/html/
                '''
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'curl http://localhost'
            }
        }
    }

    post {
        success {
            echo 'Application deployed successfully!'
        }

        failure {
            echo 'Deployment failed!'
        }
    }
}
