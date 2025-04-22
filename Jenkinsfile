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

        stage('Verify Go Installation') {
            steps {
                bat 'go version'
            }
        }

        stage('Build') {
            steps {
                bat 'go build -o app.exe'
            }
        }

        stage('Run') {
            steps {
                bat 'app.exe'
            }
        }
    }
}
