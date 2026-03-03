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
                pip install -r requirements.txt
                 
                '''
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh '''
                    
                    echo "doing test stuff..."

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