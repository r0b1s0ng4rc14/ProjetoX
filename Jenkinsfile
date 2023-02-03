pipeline {
    agent any 

    stages{
        stage('Build Image') {
            steps {
                script {
                    dockerapp = docker.build("robisongarcia/mysql}", '-f ./src/Dockerfile .') 
                }
            }
        }

        stage('Push Image'){
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub'){
                        dockerapp.push()
                    }
                }
            }
        }
    }
}
