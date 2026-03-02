pipeline {
    agent {
        docker {
            image 'python:3.12'
        }
    }

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python hello.py
                python hello.py --name=Brad
                '''
            }
        }

        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh 'echo "doing delivery stuff.."'
            }
        }
    }
}