pipeline {
    agent any

    stages {
        stage('Compile Java') {
            steps {
                bat 'javac main.java'
            }
        }

        stage('Run Java') {
            steps {
                bat 'java Main'
            }
        }
    }
}
