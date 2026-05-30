pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t demo-java-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run --rm demo-java-app'
            }
        }
    }
}