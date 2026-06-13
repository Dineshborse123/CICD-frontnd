pipeline{
    stage{
        stage('install') {
            steps{
                sh 'npm install'
            }
        }
        stage ('Build'){
            steps{
                sh 'npm run build'
            }
        }
        stage ('Deploy'){
            steps{
                echo 'Deploying...'
                sh '''
                cp -r dist/* /var/www/html/
                sudo systemctl restart nginx
                '''
            }
        }
    }
}