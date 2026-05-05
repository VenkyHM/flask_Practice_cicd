pipeline {
    agent {label 'Jenkins'}

    environment {
        MONGO_URI = "mongodb://localhost:27017/test_student_db"
        SECRET_KEY = "testsecret"
    }

    stages {

        stage('Build') {
            steps {
                sh '''
                python3 -m venv venv
                ./venv/bin/pip install --upgrade pip
                ./venv/bin/pip install -r requirements.txt
                '''
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