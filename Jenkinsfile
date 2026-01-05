pipeline {
    agent any
    
    environment {
        DEPLOY_PATH = '/var/www/fymio.us'
    }
    
    stages {
        stage('Deploy') {
            steps {
              sh '''
                scp -o StrictHostKeyChecking=no index.html root@172.17.0.1:${DEPLOY_PATH}/
                scp -o StrictHostKeyChecking=no -r congrats/ root@172.17.0.1:${DEPLOY_PATH}/
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
