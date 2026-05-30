pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "bssshanky1991/demo-java-app"
    }

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t %DOCKER_IMAGE%:latest .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run --rm %DOCKER_IMAGE%:latest'
            }
        }
    }

    post {
        success {
            echo 'Docker Build and Run Successful!'
        }

        failure {
            echo 'Build Failed!'
        }
    }
}