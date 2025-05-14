pipeline {
    agent any
    tools {
        // Use the SonarQube Scanner configured in Jenkins
        sonarScanner 'SonarScanner'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Jigyansu1234/Jigyansu1234.git'
            }
        }
        stage('Build') {
            steps {
                echo 'No build tools used — skipping build step.'
            }
        }
        stage('SonarQube Code Scan') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'sonar-scanner -Dsonar.projectKey=Code-Scan -Dsonar.sources=.'
                }
            }
        }
    }
}
