pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs() // Ensure no cached data
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sriravi25/nginx_CICD.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    echo "Copying updated index.html to /var/www/html"
                    sudo cp index.html /var/www/html/index.html
                    sudo systemctl restart nginx
                '''
            }
        }
    }
}
