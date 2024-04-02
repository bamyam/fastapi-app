pipeline {
    agent any

    stages {
        stage('pre clean') {
            steps {
              sh 'docker compose down -v'
            }
        }
        stage('git scm update') {
            steps {
                git url: 'https://github.com/bamyam/fastapi-app.git', branch: 'main'
            }
        }
        stage('docker build and push') {
            steps {
                sh'''
                docker compose up --build -d
                '''
            }
        }
    }
}
