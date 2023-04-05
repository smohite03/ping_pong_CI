pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                docker build -t shashwat0309/pingpongci:latest .
                docker login -u shashwat0309 -p Shashwat@0309
            }
        }
        stage('Deploy') {
            steps {
                docker push shashwat0309/pingpongci:latest
            }
        }
    }
}