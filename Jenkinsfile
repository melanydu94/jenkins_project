pipeline {
    agent any

    stages {
        
        stage('Clean Docker Images') {
        catchError(buildResult: 'SUCCESS', stageResult: 'SUCCESS') {
            sh '`docker rmi -f $(docker images -q)`'
            }
        }

        
        stage('Build Docker image') {
            
            steps {
                sh '''
                export PATH=/sbin:/usr/sbin:/bin:/usr/bin:/usr/local/bin/
                docker-compose up
                '''
            }

        }
    }
}
