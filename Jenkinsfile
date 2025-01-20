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
          stage('Generate a webhook build') {
            steps {
                bat 'npm run build'
            }
        }
          stage('Deploy') {
            steps {
                echo 'Deploying.......'
            }
        }
          stage('Application Deployed') {
            steps {
                echo 'Deployment Successful!!!!!'
            }
        }
        
    }
}
