pipeline {
    agent any

    stages {
        stage('Node Build') {
            agent {
                docker {
                    image 'node:18-slim'
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

        stage('Docker Tasks') {
            agent any // This runs directly on Jenkins host
            steps {
                sh '''
                    docker --version
                    docker inspect -f . node:18-slim
                    docker build -t my-app .
                '''
            }
        }
    }
}
