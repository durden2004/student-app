pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/durden2004/student-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t student-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f student-app || true'
                sh 'docker run -d -p 80:80 --name student-app student-app'
            }
        }
    }
}
