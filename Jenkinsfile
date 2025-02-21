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
                bash 'npm install'
            }
        }

        stage('Start Application') {
            steps {
                bash 'npm start &'
            }
        }

        stage('Run Tests') {
            steps {
                bash 'npm test'
            }
        }
    }
}
