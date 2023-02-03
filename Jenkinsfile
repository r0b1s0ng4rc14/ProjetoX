pipeline {
    agent any 

    stages {
        stage('Build Imagel') {
            steps {
                script {
                    dockerapp = docker.build("robisongarcia/mysql", '-f ./src/Dockerfile ./src') 
                }
            }
        }
    }
}
