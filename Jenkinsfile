pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sriravi25/nginx_CICD.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    sudo cp index.html /var/www/html/index.html
                    sudo systemctl restart nginx
                '''
            }
        }
    }
}
