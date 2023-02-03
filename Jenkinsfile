pipeline {
    agent any 
        stage('Build Image') {
            steps {
                script {
                    dockerapp = docker.build("robisongarcia/mysql:${env.BUILD_ID}", '-f ./src/Dockerfile .') 
                }
            }
        }
        stage('Push Image') {
            docker.withRegistry('https://registry.hub.docker.com', 'dockerhub'){
                dockerapp.push('latest')
                dockerapp.push('${env.BUILD_ID}')
            }

        }
    }
}
