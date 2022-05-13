pipeline {
  environment {
    registry = "vishnupriya0805/docker-kube"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent{
  kubernetes {
      label 'jdkpod'
      defaultContainer 'jdk'
    }
  }
  stages {
    stage('Build') {
       steps {
         sh "mvn clean install"
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
