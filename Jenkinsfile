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
                 cd myapp
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