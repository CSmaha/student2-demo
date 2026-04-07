pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }a

        stage('Checkout') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Snyk Scan') {
            steps {
                echo 'Snyk scan stage'
            }
        }

        stage('SonarQube Scan') {
            steps {
                echo 'SonarQube scan stage'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t student2-demo:latest .'
            }
        }

        stage('Run App') {
            steps {
                sh 'docker rm -f student2-app || true'
                sh 'docker run -d --name student2-app -p 3002:3000 student1-demo:latest'
            }
        }

        stage('ZAP Scan') {
            steps {
                echo 'ZAP scan stage'
            }
        }

        stage('Kubernetes Deploy') {
            steps {
                echo 'Kubernetes deploy stage'
            }
        }
    }
}

