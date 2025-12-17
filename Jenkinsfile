pipeline {
    agent any
    
    environment {
        DEPLOY_PATH = '/var/www/fymio.us'
    }
    
    stages {
        stage('Deploy') {
            steps {
                sh '''
                    # Deploy to host via SSH
                    scp -o StrictHostKeyChecking=no index.html root@172.17.0.1:${DEPLOY_PATH}/
                    
                    # If you have other files/folders later:
                    # scp -o StrictHostKeyChecking=no -r assets/ root@172.17.0.1:${DEPLOY_PATH}/
                '''
            }
        }
    }
    
    post {
        success {
            echo 'Deployment successful! Visit https://fymio.us'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
