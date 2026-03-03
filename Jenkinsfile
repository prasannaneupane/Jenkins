pipeline {
    agent { 
        node {
            label 'python-agent'
        }
    }
    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo "Building..."
                sh '''
                    cd myapp
                    echo "doing build stuff..."
                    apt-get update
                    apt-get install -y python3-venv
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh '''
                    cd myapp
                    echo "doing test stuff..."
                    python3 hello.py
                    python3 hello.py --name=Prasanna
                '''
            }
        }

        stage('Deliver') {
            steps {
                echo "Delivering..."
                sh '''
                    echo "doing delivery stuff..."
                '''
            }
        }
    }
}