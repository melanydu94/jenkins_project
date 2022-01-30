pipeline {
    agent any

    stages {
        
        stage('Build Docker image') {
            agent dockerfile true
            steps {
                sh 'gradle --version'
            }

        }
            
        stage('Build') {
            steps {
                sh '''
                export PATH=/sbin:/usr/sbin:/bin:/usr/bin:/usr/local/bin/
                npm install
                npm start
                '''
            }
        }
    }
}

