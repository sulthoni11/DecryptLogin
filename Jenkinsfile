pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sulthoni11/DecryptLogin'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
    }
}
