pipeline {
    agent any

    stages {
        stage('Update') {
            steps {
                sh 'sudo apt update'
            }
        }
        stage('Install') {
            steps {
                sh 'sudo apt install apache2 -y'
            }
        }
        stage('Start') {
            steps {
                sh 'sudo systemctl start apache2'
            }
        }
        stage('Check status') {
            steps {
                sh 'sudo systemctl status apache2'
            }
        }
        stage('Check version') {
            steps {
                sh 'apache2 -v'
            }
        }
        stage('Checking for 4xx and 5xx errors') {
            steps {
                sh 'sudo grep " 4" /var/log/apache2/access.log || echo "Coudnt find 4** errors"'
                sh 'sudo grep " 5" /var/log/apache2/access.log || echo "Coudnt find 5** errors"'
            }
        }
        
    }
}
