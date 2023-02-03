pipeline {
    agent any 

    stages {
        stage (teste) {
            steps{
                sh 'ls -lah'
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
