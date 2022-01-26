pipeline {
    agent any

    stages {
        stage('Clean Docker Images') {
        catchError(buildResult: 'SUCCESS', stageResult: 'SUCCESS') {
            sh '`docker rmi -f $(docker images -q)`'
            }
        }
        stage('Build Garde-ma-cle') {
        script {
            app = docker.build('jenkins-project', '--memory "1024m" --cpu-quota="100000" --memory-swap="1g" .')
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
