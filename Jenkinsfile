pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Dimitar-Dechevski/Student-Registry-App.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat "npm install"
            }
        }

        stage('Run Application') {
            steps {
                bat "start /b npm start"
            }
        }

        stage('Run Tests') {
            steps {
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
