pipeline {
  agent any
  parameters {
    credentials credentialType: 'com.cloudbees.plugins.credentials.impl.UsernamePasswordCredentialsImpl', defaultValue: 'dockercred', description: 'Please Enter Docker Creds', name: 'DockerCreds', required: true
    }

  stages {

      stage ('Build') {
          
         steps {
             
               git 'https://github.com/MallikarjunagoudaCM/jenkinspipe1.git'
               sh "docker login -u $MYVARNAME_USR -p $MYVARNAME_PSW"
         }       
             

         }
      }
}
