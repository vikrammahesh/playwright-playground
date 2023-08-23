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
                npm ci
            }
        }

      
    }
}
