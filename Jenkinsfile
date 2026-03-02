pipeline {
    agent {
        docker {
            image 'python:3.13.12-slim-trixie'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/prasannaneupane/Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'python -m pip install --upgrade pip'
                sh 'python -m pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'python hello.py'
                sh 'python hello.py --name=Brad'
            }
        }

        stage('Deliver') {
            steps {
                echo 'Delivering...'
            }
        }
    }
}