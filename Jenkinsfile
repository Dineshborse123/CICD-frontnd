pipeline {
    agent any

    stages {

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
               sudo cp -r dist/* /var/www/html/
                sudo systemctl restart nginx
                '''
            }
        }
    }
}