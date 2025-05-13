pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Jigyansu1234/Jigyansu1234.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build tools used — skipping build step.'
            }
        }

        stage('SonarQube Code Scan') {
            steps {
                sh '''
                sonar-scanner \
                  -Dsonar.projectKey=Code-Scan \
                  -Dsonar.sources=. \
                  -Dsonar.host.url=http://3.87.74.195:9001 \
                  -Dsonar.token=sqp_0f0f77c6c4e1cd84d4d2b4352d1a6a0844ac6193
                '''
            }
        }
    }
}
