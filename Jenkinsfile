pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/MHasan-sys/flask-app-jenkins.git'
            }
        }
        stage('Build & Run Docker') {
            steps {
                script {
                    // Build and run using docker-compose
                    sh 'docker-compose down'    // stop any running containers
                    sh 'docker-compose up -d --build'
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
