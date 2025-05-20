pipeline {
    agent any

    tools {
        nodejs 'Node16' // Harus cocok dengan nama di konfigurasi Jenkins
    }

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
