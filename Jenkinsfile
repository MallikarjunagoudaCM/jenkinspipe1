pipeline {
  agent any
  parameters {
  credentials credentialType: 'org.jenkinsci.plugins.plaincredentials.impl.StringCredentialsImpl', defaultValue: '', description: 'Please Enter Docker Creds', name: 'DockerCreds1', required: true
}

  stages {

      stage ('Build') {
          
         steps {
             withCredentials([usernamePassword(
                 credentialsId: '${DockerCreds1}',
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
