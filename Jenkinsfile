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
        sh '''
            cd myapp
            apt-get update
            apt-get install -y python3-venv
            python3 -m venv venv
            . venv/bin/activate
            pip install --upgrade pip
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