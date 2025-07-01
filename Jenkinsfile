pipeline {
  agent any

  environment {
    IMAGE = "myapp:latest"
    TARFILE = "myapp.tar"
  }

  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/HARSHITHA-G-M/CI-CD-Pipeline-using-Jenkins-Ansible-Docker.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t $IMAGE .'
        sh 'docker save $IMAGE > $TARFILE'
      }
    }

    stage('Copy to Remote') {
      steps {
        sh 'scp $TARFILE user@172-31-13-161:/home/user/'
      }
    }

    stage('Ansible Deploy') {
      steps {
        sh 'ansible-playbook -i inventory.ini deploy.yml'
      }
    }
  }
}

