pipeline {
    agent any
    tools {
        maven 'Maven 3.8.1'  // Install Maven if needed
    }
    environment {
        SONARQUBE = 'sonarqube'
    }
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Jigyansu1234/Jigyansu1234.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv("${SONARQUBE}") {
                    sh 'mvn sonar:sonar'
                }
            }
        }
    }
}
