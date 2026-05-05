pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/VenkyHM/CICD-Pipeline-FlaskApp.git'
            }
        }

        stage('Build') {
            steps {
                sh '''
                python3 -m venv venv
                ./venv/bin/pip install --upgrade pip
                ./venv/bin/pip install -r requirements.txt
                ./venv/bin/pip install pytest
                '''
            }
        }

        stage('Start MongoDB') {
            steps {
                sh 'sudo systemctl start mongod'
            }
        }

        stage('Test') {
            steps {
                sh './venv/bin/pytest -v'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                pkill -f app.py || true
                nohup ./venv/bin/python app.py > output.log 2>&1 &
                sleep 5
                '''
            }
        }
    }

    post {
        success {
            echo 'Build Successful!'
        }
        failure {
            echo 'Build Failed!'
        }
    }
}