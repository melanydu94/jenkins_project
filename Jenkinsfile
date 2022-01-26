pipeline {
    agent any

    stages {
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
