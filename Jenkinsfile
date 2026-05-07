pipeline {
    agent {label 'Jenkins'}

    environment {
        MONGO_URI = "mongodb://localhost:27017/test_student_db"
        SECRET_KEY = "testsecret"
    }

    stages {

        stage('Checkout') {
            steps {
                // Pull latest code from GitHub
                checkout scm
            }
        }

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
                # Stop any existing app.py process
                pkill -f app.py || true

                # Relaunch Flask app in background
                nohup ./venv/bin/python app.py > output.log 2>&1 &
                sleep 5
                '''
            }
        }
    }

    post {

        success {
            echo '✅ Build Successful!'

            mail to: 'venkat.hm786@gmail.com',
            subject: "SUCCESS: Jenkins Build ${BUILD_NUMBER}",
            body: "Build Successful"
        }

        failure {
            echo '❌ Build Failed!'

            mail to: 'venkat.hm786@gmail.com',
            subject: "FAILED: Jenkins Build ${BUILD_NUMBER}",
            body: "Build Failed"
        }
    }
}