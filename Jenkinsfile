pipeline {
    agent any
    environment {
        NETLIFY_AUTH_TOKEN = credentials('NETLIFY_AUTH_TOKEN')
        NETLIFY_SITE_ID = 'c33c1741-3af4-4f9b-941c-e18db54d440c'  
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Netlify CLI') {
            steps {
                bat 'npm install netlify-cli'
            }
        }
        stage('Deploy to Netlify') {
            steps {
                bat 'npx netlify deploy --dir=. --prod --auth=%NETLIFY_AUTH_TOKEN% --site=%NETLIFY_SITE_ID%'
            }
        }
    }
}
