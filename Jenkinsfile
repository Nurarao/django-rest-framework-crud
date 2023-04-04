pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements/development.txt'
            }
        }
        stage('Build') {
            steps {
                sh 'python manage.py migrate'
                sh 'python manage.py collectstatic --noinput'
                sh 'python manage.py test'
            }
        }
        stage('Deploy') {
            steps {
                echo "deploy"
            }
        }
    }
}

