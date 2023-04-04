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
                sh 'pip install -r requirements.txt'
                sh 'python manage.py migrate'
                sh 'python manage.py collectstatic --noinput'
            }
        }
        stage('Deploy') {
            steps {
                echo "deploy"
            }
        }
    }
}

