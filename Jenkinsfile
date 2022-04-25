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
    }
   }