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
        bash 'curl -fsSL https://deb.nodesource.com/setup_18.x | bash -'
        bash 'sudo apt-get install -y nodejs'
        bash 'node -v'
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
