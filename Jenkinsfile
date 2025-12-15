pipeline {
    agent any

    environment {
        SONARQUBE = 'SonarQube' // Your SonarQube server name in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/puppalashivasurya/my2ndproject.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Security Scan') {
            steps {
                // Using Trivy to scan the project
                sh 'trivy fs .'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
