pipeline {
    agent any

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

        stage('Deploy to Heroku') {
            when {
                branch 'development'
            }
            steps {
                withCredentials([string(credentialsId: 'HEROKU_API_KEY', variable: 'HEROKU_API_KEY')]) {
                    sh '''
                        echo "Deploying to Heroku..."
                        git remote add heroku https://heroku:$HEROKU_API_KEY@git.heroku.com/NAMA-APP.git || true
                        git push heroku development:main --force
                    '''
                }
            }
        }
    }
}
