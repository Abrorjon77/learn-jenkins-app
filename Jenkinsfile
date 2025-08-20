pipeline {
    agent any

    stages {
        stage('Build App') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    node -v
                    npm ci
                    npm run build
                '''
            }
        }

        stage('Build Docker Image') {
            agent any
            steps {
                sh '''
                    docker --version
                    docker build -t my-app .
                '''
            }
        }
    }
}
