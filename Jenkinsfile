pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'docker version'
                sh 'docker compose -f  docker-compose.yml up --build --detach'
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