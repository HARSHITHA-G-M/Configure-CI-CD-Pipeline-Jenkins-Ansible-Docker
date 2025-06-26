pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/HARSHITHA-G-M/Configure-CI-CD-Pipeline-Jenkins-Ansible-Docker.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                dir('docker') {
                    sh 'docker build -t myapp .'
                }
            }
        }

        stage('Deploy with Ansible') {
            steps {
                dir('ansible') {
                    sh 'ansible-playbook -i /etc/ansible/hosts deploy.yml'
                }
            }
        }
    }
}

