pipeline {
  agent any
  parameters {
    credentials credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl', defaultValue: 'dockercred', description: 'Please Enter Docker Creds', name: 'DockerCreds', required: true
    }

  stages {

      stage ('Build') {
          
         steps {
             withCredentials([usernamePassword(
                 credentialsId: '${DockerCreds}',
                 usernameVariable: 'DEPLOY_USERNAME',
                 passwordVariable: 'DEPLOY_PASSWORD',
                )])
             
               git 'https://github.com/MallikarjunagoudaCM/jenkinspipe1.git'
               sh 'docker login -u $DEPLOY_USERNAME -p $DEPLOY_PASSWORD'
         }       
             

         }
      }
}
