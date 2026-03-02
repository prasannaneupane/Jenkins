pipeline {
    agent {
        label 'docker-agent-python'
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
                    sh 'python3 -m pip install --upgrade pip'
                    sh 'pip install -r requirements.txt'
                }
            }
        }

        stage('Test') {
            steps {
                dir('myapp') {
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