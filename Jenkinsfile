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
        
    }
}
