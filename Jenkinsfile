pipeline {
    agent any 

    stages {
        stage (teste) {
            step{
                sh "ls -lah"
            }
        }
        stage('Build Imagel') {
            steps {
                script {
                    dockerapp = docker.build("robisongarcia/mysql", '-f ./src/Dockerfile ./src') 
                }
            }
        }
    }
}
