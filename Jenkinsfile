pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node: alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    set -ex
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
