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
                sh 'python manage.py collectstatic --noinput'
                // sh 'python3 manage.py collectstatic --noinput'
            }
        }
        stage('Deploy') {
            steps {
                echo "deploy"
            }
        }
    }
}

    // stage('Deploy to Server 1') {
    //         environment {
    //             SSH_USER = 'your_ssh_user'
    //             SERVER_IP = 'your_server_1_ip_address'
    //             APP_DIR = 'your_app_directory'
    //         }
    //         steps {
    //             sshagent (credentials: ['your_ssh_credentials']) {
    //                 sh "ssh -o StrictHostKeyChecking=no $SSH_USER@$SERVER_IP 'cd $APP_DIR && git pull origin main && pip install -r requirements.txt && python manage.py migrate && sudo systemctl restart gunicorn'"
    //             }
    //         }
    //     }
    //     stage('Deploy to Server 2') {
    //         environment {
    //             SSH_USER = 'your_ssh_user'
    //             SERVER_IP = 'your_server_2_ip_address'
    //             APP_DIR = 'your_app_directory'
    //         }
    //         steps {
    //             sshagent (credentials: ['your_ssh_credentials']) {
    //                 sh "ssh -o StrictHostKeyChecking=no $SSH_USER@$SERVER_IP 'cd $APP_DIR && git pull origin main && pip install -r requirements.txt && python manage.py migrate && sudo systemctl restart gunicorn'"
    //             }