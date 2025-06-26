pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/yourusername/jenkins-ansible-docker-cicd.git'
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

