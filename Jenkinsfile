pipeline {
    agent any
    tools {nodejs "node"}
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
                    sudo npx playwright install-deps
                    sudo npx playwright install
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
