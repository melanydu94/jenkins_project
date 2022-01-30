pipeline {
    agent any

    stages {
        
        stage('Build Docker image') {
            agent {
                docker {
                    image 'gradle:6.7-jdk11'
                    // Run the container on the node specified at the top-level of the Pipeline, in the same workspace, rather than on a new node entirely:
                    reuseNode true
                }
            }
            
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

