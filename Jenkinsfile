pipeline {
    agent any

    stages {
        stage('git') {
            steps {
                checkout scm
            }
        }
        stage('build') {
            steps {
            sh 'docker build -t sample1 .'
            sh 'docker tag sample1 jayak8309101680/frontend:v3'
            }
        }
        stage('deploy') {
            steps {
                sshagent(credentials : ['terraform']) {
                    sh 'ssh -o StrictHostKeyChecking=no ubuntu@52.91.164.71 docker run -itd -p 8082:8081 jayak8309101680/frontend:v2'
                }
            }
        }
    }
}
