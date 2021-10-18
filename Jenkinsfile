pipeline {
  agent any
 stages {
      
       stage('Building Image') {
         steps{
             sh 'docker build -t karate-docker /home/billion/karate-sample'
         }
         }
    
   stage('clone the maven project'){
     steps {
       git 'https://gitlab.com/47billion/nextgenproduct/documentunderstanding/testing/apisanity.git'
     }
   }
       stage('run image') {
         steps {  
           sh 'docker run -ti karate-docker mvn clean install -Dtest=UsersRunner'
               }
       }

  }
}
