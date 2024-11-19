pipeline {
    agent any

    environment {
        NODE_VERSION = '20.x'
    }

    tools {
        nodejs "${NODE_VERSION}"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Dimitar-Dechevski/Student-Registry-App.git'
            }
        }

        stage('Setup Node.js') {
            steps {
                bat '''
                node --version
                npm --version
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                bat "npm install"
            }
        }

        stage('Run Application') {
            steps {
                bat "npm start &"
            }
        }

        stage('Run Tests') {
            steps {
                bat "chmod 0777 ./node_modules/.bin/mocha"
                bat "npm test"
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution finished.'
        }
    }
}