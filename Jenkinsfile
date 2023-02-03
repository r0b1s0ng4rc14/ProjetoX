pipeline {
    agent any 

    stages{
        stage('Build Imagel') {
            steps {
                script {
                    dockerapp = docker.build("robisongarcia/mysql:v${env.BUILD_ID}", '-f ./src/Dockerfile .') 
                }
            }
        }

        stage('Push Image'){
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub'){
                        dockerapp.push('latest')
                        dockerapp.push('${env.BUILD_ID}')
                    }
                }
            }
        }
    }
}
