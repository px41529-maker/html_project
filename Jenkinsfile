pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/px41529-maker/html_project.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo cp index.html /var/www/html/
                sudo cp style.css /var/www/html/
                sudo cp script.js /var/www/html/
                '''
            }
        }

        stage('Verify') {
            steps {
                sh 'ls -l /var/www/html/'
            }
        }
    }

    post {
        success {
            echo 'Website deployed successfully to EC2'
        }
    }
}
