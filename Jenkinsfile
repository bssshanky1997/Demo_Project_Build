pipeline {
agent any

```
environment {
    DOCKER_IMAGE = "bssshanky1991/demo-java-app"
}

stages {

    stage('Build Docker Image') {
        steps {
            bat 'docker build -t %DOCKER_IMAGE%:latest .'
        }
    }

    stage('Docker Hub Login') {
        steps {
            withCredentials([usernamePassword(
                credentialsId: 'dockerhub-creds',
                usernameVariable: 'DOCKER_USER',
                passwordVariable: 'DOCKER_PASS'
            )]) {
                bat 'echo %DOCKER_PASS% | docker login -u %DOCKER_USER% --password-stdin'
            }
        }
    }

    stage('Push Docker Image') {
        steps {
            bat 'docker push %DOCKER_IMAGE%:latest'
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
        echo 'Docker Image Build, Push and Run Successful!'
    }

    failure {
        echo 'Build Failed!'
    }
}
```

}
