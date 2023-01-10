pipeline{
  agent any
  stages{
    stage("Git Checkout"){
      steps{
            git credentialsId: 'github', url: 'https://github.com/beerejhansirani2408/hello-world-war.git'
           }
          }
     stage("Maven clean Build"){
       steps{
            sh "mvn clean package"
             }
            }
     stage("Building Docker Image"){
       steps{
          sh "docker build -t hello-world/myapp:1.0 .
               }
             }
           }
        }
     }
  
