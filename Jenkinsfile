pipeline {
    agent any
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
                withSonarQubeEnv('SonarQube') { // Use the SonarQube environment configured in Jenkins
                    sh '''
                        sonar-scanner \
                        -Dsonar.projectKey=Code-Scan \
                        -Dsonar.sources=. \
                        -Dsonar.host.url=http://54.221.0.204:9001/ 
                        -Dsonar.login=sqp_0f0f77c6c4e1cd84d4d2b4352d1a6a0844ac6193
                    '''
                }
            }
        }
    }
}
