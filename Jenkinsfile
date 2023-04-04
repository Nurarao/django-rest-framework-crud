pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Build') {
            steps {
                sh 'pip3 install -r requirements.txt'
                sh 'python3 manage.py migrate'
#                sh 'python3 manage.py collectstatic --noinput'
            }
        }
        stage('Deploy') {
            steps {
                echo "deploy"
            }
        }
    }
}

