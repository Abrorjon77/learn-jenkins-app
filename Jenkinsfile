pipeline {
    agent any

    stages {
        stage('Build') {
                }
            }
            steps {
                sh '''
                    ls -la
                    node -v
                    npm -v
                    npm ci
                    npm run build
                    ls -la
                '''

            }
        }
    }
}