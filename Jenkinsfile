pipeline {
    agent any

    environment {
        GO111MODULE = 'on'
    }

    tools {
        go 'Go_1.19' // Make sure Go_1.19 (or your version) is installed in Jenkins Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'go mod init goproject || true' // Initialize module if not already done
                sh 'go build -o app'
            }
        }

        stage('Run') {
            steps {
                sh './app'
            }
        }
    }
}
