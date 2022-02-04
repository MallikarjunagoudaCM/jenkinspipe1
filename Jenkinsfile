pipeline {
  agent any
  parameters {
    credentials credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl', defaultValue: 'dockertest', description: 'Please enter Docker creds', name: 'DockerCreds', required: true
    string description: 'Please Enter the Docker Username.', name: 'Username'
    password defaultValue: '', name: 'Password'
  }

  stages {

      stage ('Build') {
          
         steps {
             withCredentials([usernamePassword(
                 credentialsId: '${DockerCreds}',
                 usernameVariable: 'DEPLOY_USERNAME',
                 passwordVariable: 'DEPLOY_PASSWORD',
                )]) {
             
               git 'https://github.com/MallikarjunagoudaCM/jenkinspipe1.git'
               sh ('docker login -u $DEPLOY_USERNAME -p $DEPLOY_PASSWORD')
                }
         }       
             
        
         }    
    stage ('docker login') {
        steps {             
               
               sh 'docker login -u ${Username} -p ${Password}'
                 
    }   

         }
      }
}
