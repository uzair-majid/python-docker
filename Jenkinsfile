pipeline {
    agent any
    environment {
      
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'docker version'
                sh 'docker compose -f  docker-compose.yml up --build --detach'
                sh “aws ecr get-login-password -- region ${AWS_DEFAULT_REGION} | docker login -- username AWS -- password-stdin ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com”
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'sleep 2'
                sh 'curl http://localhost:8000/initdb'
                sh 'sleep 2'
                sh 'curl http://localhost:8000/widgets'
                

            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
		  

            }
        }
    }
}