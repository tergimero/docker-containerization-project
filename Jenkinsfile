
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Installing Flask dependencies...'
                sh '''
                    python3 -m venv .jenkins-venv
                    .jenkins-venv/bin/pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running automated Flask tests...'
                sh '.jenkins-venv/bin/python -m unittest discover -s tests -v'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Simulating Flask deployment...'
                sh '.jenkins-venv/bin/python -m compileall -q app'
                echo 'Deployment simulation completed!'
            }
        }
    }
}
      
