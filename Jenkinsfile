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

        stage('Build') {
            steps {
                bat '''
                    set GOOS=windows
                    set GOARCH=amd64
                    go version
                    go build -o app.exe
                '''
            }
        }

        stage('Run') {
            steps {
                bat 'app.exe'
            }
        }
    }
}
