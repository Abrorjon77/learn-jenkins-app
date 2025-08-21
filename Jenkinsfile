pipeline {
    agent any

    stages {
        stage('Build App with Node') {
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

        stage('Pull Docker Image') {
            agent any  // <--- runs on Jenkins host
            steps {
                sh '''
                    docker pull node:18-alpine
                '''
            }
        }
    }
}
