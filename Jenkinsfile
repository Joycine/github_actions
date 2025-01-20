pipeline {
    agent any

    //environment {
  //      SLACK_WEBHOOK_URL = "https://hooks.slack.com/services/your/slack/webhook" // Replace with your Slack Webhook URL
   // }

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
          stage('Lint and Test in Parallel') {
            parallel {
                stage('Lint the project') {
                    steps {
                        retry(3) { // Retry mechanism for this stage
                        bat 'npm run lint'
                    }
                }
               // stage('Run Tests') {
                //    steps {
                //        bat 'npm test' // Add your test command here
                //    }
                }
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
    post {
        success {
            echo 'Pipeline executed successfully!'
         //   slackSend(channel: '#your-channel', message: "Build SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER} (${env.BUILD_URL})", webhookTokenCredentialId: 'slack-webhook-token')
        }
        failure {
            echo 'Pipeline failed!'
        //    slackSend(channel: '#your-channel', message: "Build FAILURE: ${env.JOB_NAME} #${env.BUILD_NUMBER} (${env.BUILD_URL})", webhookTokenCredentialId: 'slack-webhook-token')
        }
    }
}
