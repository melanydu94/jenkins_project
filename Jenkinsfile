pipeline {
    agent any

    stages {
        stage('NPM Build') {
          steps {
            sh "npm install"
            sh "npm start"
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
