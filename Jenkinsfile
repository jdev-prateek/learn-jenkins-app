pipeline {
    agent any
    
    stages {
        stage("hello") {
            agent {
                docker {
                    image "node:18-alpine"
                    reuseNode true
                 }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }

        stage("tests") {
            steps{
                echo "Test stage"
            }
        }
    }
}