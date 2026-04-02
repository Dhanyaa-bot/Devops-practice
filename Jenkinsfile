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
        // 1. Kill ANY container using port 3000 (even if it has a different name)
              sh "docker ps -q --filter publish=3000 | xargs -r docker stop"
        
        // 2. Remove the old container name
              sh 'docker rm -f mycontainer || true'
        
        // 3. Run the new one
              sh 'docker run -d -p 3000:3000 --name mycontainer myapp'
         }
      }
   }
