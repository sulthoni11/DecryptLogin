pipeline {
    agent any

    tools {
        nodejs 'Node16'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'development', url: 'https://github.com/sulthoni11/DecryptLogin'
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
