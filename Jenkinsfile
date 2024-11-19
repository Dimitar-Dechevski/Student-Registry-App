pipeline {
    agent any

    environment {
        NODE_VERSION = '20.x'
    }

    tools {
      nodejs "${NODE_VERSION}"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Dimitar-Dechevski/Student-Registry-App.git'
            }
        }
        stage('Build') {
            steps {
             script {
                    bat "npm install"
                }
            }
        }
        stage('Start') {
            steps {
                script {
                    bat "npm start &"
                }
            }
        }
        stage('Test') {
            steps {
             script {
                    bat "chmod 0777 ./node_modules/.bin/mocha"
                    bat "npm test"
                }
            }
        }
    }
}