pipeline {
    agent any

    environment {
        NETLIFY_AUTH_TOKEN = credentials('NETLIFY_AUTH_TOKEN')
    }

    stages {
        stage('Install Netlify CLI') {
            steps {
                bat 'npm install netlify-cli'
            }
        }

        stage('Deploy to Netlify') {
            steps {
                bat 'npx netlify deploy --dir=. --prod --auth=%NETLIFY_AUTH_TOKEN% --site=f35f05ff-2049-4e27-a8c4-a44170b30c43 --json'
            }
        }
    }
}
