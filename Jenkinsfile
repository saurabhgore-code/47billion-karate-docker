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
       stage('run test cases') {
         steps {  
           sh 'mvn clean install -Dtest=UsersRunner'
               }
       }

  }
}
