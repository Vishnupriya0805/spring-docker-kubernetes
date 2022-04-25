pipeline{
    agent any
    stages {
        stage('Build') {
            steps{
            echo 'building.....'
             }
        }
        stage('Build Docker Image') {
                    steps {
                        script {
                          bat 'docker build -t vishnupriya0805/my-app-1.0 .'
                        }
                    }
        }
        stage('Deploy Docker Image') {
                    steps {
                        script {
                         withCredentials([string(credentialsId: 'dockerhub', variable: 'Dockerhub')]) {
                            bat 'docker login -u vishnupriya0805 -p ${Dockerhub}'
                         }
                         bat 'docker push vishnupriya0805/my-app-1.0'
                        }
                    }
        }
    }
   }