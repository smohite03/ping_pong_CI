pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git branch: 'master', url: 'https://github.com/smohite03/ping_pong_CI.git'
            }
        }

        stage('Build image') {
            steps {
                script {
                    docker.build("ping-pong-api:${env.BUILD_NUMBER}")
                }
            }
        }

        stage('Push image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'DOCKER') {
                        docker.image("ping-pong-api:${env.BUILD_NUMBER}").push()
                    }
                }
            }
        }
    }
}
