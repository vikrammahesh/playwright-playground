pipeline {
    agent {
        docker { image 'node:18.17.1-alpine3.18' }
    }

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh 'node --version'
            }
        }

        stage('Install dependencies') {
            steps {
                sh  '''
                    npm ci
                    npx playwright install-deps
                    npx playwright install
                    '''
            }
        }

        stage('Tests') {
            steps {
                sh 'npm run test'
            }
        }

      
    }
}
