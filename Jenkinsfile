pipeline {
  agent any
    stages{
       stage("Build Docker Image"){
           steps{
             sh "docker build -t rishabhbhasin37/docker:${BUILD_ID} ."
          }
       }
       stage("Push Image to Repo")
          steps{
            withCredentials([string(credentialsId: 'passwd', variable: 'pass')]) {
             sh "docker login -u rishabhbhasin37 -p ${pass}"
             sh "docker push rishabhbhasin/docker:${BUILD_ID}"
            }  
           
          }
       }
 
    }  

}
