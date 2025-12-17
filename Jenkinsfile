pipeline {
    agent any
    
    stages {
        stage('Deploy') {
            steps {
                sh '''
                    # Copy files to web directory
                    cp -r * /var/www/fymio.us/
                '''
            }
        }
    }
    
    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
