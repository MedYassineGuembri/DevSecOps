pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/MedYassineGuembri/DevSecOps.git'
            }
        }

        stage('Build and Deploy to Staging') {
            steps {
                sh './scripts/deploy_staging.sh'
            }
        }

        stage('Security Review') {
            steps {
                input message: 'Please review the security report and approve to proceed.'
            }
        }

        stage('Deploy to Production') {
            steps {
                sh './deploy_production.sh'
            }
        }
    }
}
