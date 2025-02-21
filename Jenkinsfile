pipeline {
    agent any

    environment {
        NODE_VERSION = '18' // Specify the Node.js version
    }

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Setup Node.js') {
            steps {
        bat 'where node'  // Check if Node.js is installed
        bat 'node -v'     // Verify Node.js version
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Start Application') {
            steps {
                bat 'start /B npm start'
                // Wait 5 seconds to let the application initialize
                bat 'timeout /t 5'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'npm test'
            }
        }
    }
}
