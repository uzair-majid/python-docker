pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		sh docker compose -f  docker-compose.yml up --build --detach 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
		
            }
        }
    }
}

