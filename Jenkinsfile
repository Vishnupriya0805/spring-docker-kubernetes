pipeline {
  environment {
    registry = "vishnupriya0805/docker-test"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/Vishnupriya0805/spring-docker-kubernetes.git'
      }
    }
    stage('Build') {
       steps {
        echo 'building...'
       }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Deploy Image') {
      steps{
         script {
            docker.withRegistry( '', registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }
  }
}    
        
        
        
        
        
        
        
        /*stage('Build Docker Image') {
                    steps {
                        script {
                          bat 'docker build -t vishnupriya0805/my-app-1.0 .'
                        }
                    }
        }
        stage('Deploy Docker Image') {
                    steps {
                        script {
                            bat 'docker login -u vishnupriya0805 -p '
                         }
                         bat 'docker push vishnupriya0805/my-app-1.0'
                        }
                    }
        }
    }
   }*/
