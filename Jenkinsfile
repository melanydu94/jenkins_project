pipeline {
    agent any

    stages {
        stage('Pull') {
            steps {
                git ([url:'https://github.com/melanydu94/jenkins_project/', branch:'main'])
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
