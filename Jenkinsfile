pipeline {
    agent any

  /*  environment {
        SLACK_WEBHOOK_URL = "https://hooks.slack.com/services/your/slack/webhook" // Replace with your Slack Webhook URL
    }*/

    stages {
        stage('Install Dependencies') {
            steps {
                retry(3) { // Retry mechanism for this stage
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
