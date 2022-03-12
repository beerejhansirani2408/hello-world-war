pipeline{
  agent any
  stages{
    stage("Git Checkout"){
      steps{
            git credentialsId: 'github', url: 'https://github.com/beerejhansirani2408/cmr-repo.git'
           }
          }
     stage("Maven clean Build"){
       steps{
            sh "mvn clean package"
             }
            }
     stage("Building Docker Image"){
       steps{
          sh "docker build -t cmr-repo/myapp:1.0 ."
          withCredentials([string(credentialsId: 'DOCKER_HUB_CREDENTIALS', variable: 'DOCKER_HUB_CREDENTIALS')]) {
          sh "docker login -u jhansirani408 -p ${DOCKER_HUB_CREDENTIALS}"
          sh "docker tag cmr-repo/myapp:1.0 jhansirani408/cmr-repo:1.0"
          sh "docker push jhansirani408/cmr-repo:1.0"
               }
             }
           }
        }
     }
  
