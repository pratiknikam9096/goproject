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

        stage('Run Go Program') {
            steps {
                bat '''
                    go version
                    go run main.go
                '''
            }
        }
    }
}
