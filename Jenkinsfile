pipeline {
    agent any

    stages {
        
        stage('Build Docker image') {
            
            steps {
                sh '''
                export PATH=/sbin:/usr/sbin:/bin:/usr/bin:/usr/local/bin/
                docker run --name registry-jenkins
                docker start
                docker-compose up
                '''
            }

        }
    }
}
