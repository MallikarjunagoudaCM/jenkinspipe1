pipeline {
  agent any
  parameters {
  credentials credentialType: 'org.jenkinsci.plugins.plaincredentials.impl.StringCredentialsImpl', defaultValue: '', name: 'DockerCreds', required: true
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
