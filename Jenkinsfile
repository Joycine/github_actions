pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
          stage('Lint the project') {
            steps {
                bat 'npm run lint'
            }
        }
          stage('Generate a production build') {
            steps {
                bat 'npm run build'
            }
        }
          stage('Deploy to GCP') {
            steps {
                echo 'Deploying to GCP.......'
            }
        }
          stage('Application Deployed') {
            steps {
                echo 'Deployment Successful!!!!!'
            }
        }
        
    }
}
