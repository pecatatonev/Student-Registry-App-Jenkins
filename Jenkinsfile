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
                script {
                    def nodeTool = tool name: "NodeJS ${NODE_VERSION}", type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
                    env.PATH = "${nodeTool}/bin:${env.PATH}"
                }
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
