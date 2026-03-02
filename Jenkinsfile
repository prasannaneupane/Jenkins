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
                    // Upgrade pip and install dependencies
                    sh 'python3 -m pip install --upgrade pip && pip install -r requirements.txt'
                }
            }
        }

        stage('Test') {
            steps {
                dir('myapp') {
                    // Run your Python scripts
                    sh 'python3 hello.py'
                    sh 'python3 hello.py --name=Brad'
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