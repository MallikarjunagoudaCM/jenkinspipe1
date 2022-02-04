pipeline {
  agent any
  parameters {
    credentials credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl', defaultValue: 'dockertest', description: 'Please enter Docker creds', name: 'DockerCreds', required: false
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
               sh ('docker login -u $DEPLOY_USERNAME --password-stdin $DEPLOY_PASSWORD')
                }
         }       
             

         }
      }
}
