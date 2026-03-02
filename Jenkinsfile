pipeline {
    agent {
        // Use a Python Docker image directly
        docker {
            image 'devopsjourney1/myjenkinsagents:python'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone your GitHub repo from main branch
                git branch: 'main', url: 'https://github.com/prasannaneupane/Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                dir('myapp') {
                    // Upgrade pip and install dependencies
                    sh 'python3 -m pip install --upgrade pip'
                    sh 'pip install -r requirements.txt'
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