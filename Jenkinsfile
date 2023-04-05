pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t shashwat0309/pingpongci:latest .'
                sh 'docker login -u shashwat0309 -p Shashwat@0309'
            }
        }
        stage('Deploy') {
            steps {
                'sh docker push shashwat0309/pingpongci:latest'
            }
        }
    }
}