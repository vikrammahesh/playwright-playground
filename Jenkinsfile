pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Install dependencies') {
            steps {
                npm ci
            }
        }

        stage('Run test') {
            steps {
                npm run test
            }
        }
    }
}
