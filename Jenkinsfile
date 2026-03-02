pipeline {
    agent {
        docker {
            image 'python:3.12'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/prasannaneupane/Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                dir('myapp') {
                    sh 'pip install -r requirements.txt'
                }
            }
        }

        stage('Test') {
            steps {
                dir('myapp') {
                    sh 'python hello.py'
                    sh 'python hello.py --name=Brad'
                }
            }
        }

        stage('Deliver') {
            steps {
                echo 'Delivering...'
            }
        }
    }
}