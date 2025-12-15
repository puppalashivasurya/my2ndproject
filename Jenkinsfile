pipeline {
    agent any

    options {
        timestamps()
    }

    stages {

        stage('Build') {
            steps {
                echo 'Build stage running'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                echo 'SonarQube analysis stage'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Security scan stage'
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage running'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully ✅'
        }
        failure {
            echo 'Pipeline failed ❌'
        }
        always {
            echo 'Pipeline finished'
        }
    }
}
