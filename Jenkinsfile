pipeline {
    agent any

    environment {
        GO111MODULE = 'on'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Setup Go') {
            steps {
                sh '''
                    if ! command -v go &> /dev/null
                    then
                        echo "Go not found! Please install Go on Jenkins agent."
                        exit 1
                    fi
                    go version
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                    go mod init goproject || true
                    go build -o app
                '''
            }
        }

        stage('Run') {
            steps {
                sh './app'
            }
        }
    }
}
