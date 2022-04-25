pipeline{
    agent any
     tools {
            maven 'MAVEN'
        }
    stages {
        stage('Build Maven') {
            steps{
            bat "mvn -Dmaven.test.failure.ignore=true clean package"
             }
        }
    }
   }