pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/Dhanyaa-bot/Devops-practice.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t myapp  .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f mycontainer || true'
                sh 'docker run -d -p 3000:3000 --name mycontainer myapp'
            }
        }
    }
}

