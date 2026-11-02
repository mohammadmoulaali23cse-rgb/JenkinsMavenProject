pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code fetched from GitHub'
            }
        }

        stage('Verify Tools') {
            steps {
                bat 'java -version'
                bat 'mvn -version'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'GitHub + Jenkins + Maven Build Successful!'
        }

        failure {
            echo 'Build Failed!'
        }
    }
}