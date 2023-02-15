pipeline{
     agent  {label "agentfarm" }
     stages {
          stage( 'Delete the workspace') {
              steps{
                  cleanWs()
              }
          }
       stage( ' Installing Maven ') {
           steps {
               sh 'sudo apt-get update -y && sudo apt-get upgrade -y'
               sh 'sudo apt install -y wget tree unzip openjdk-11-jdk maven'
           }
          }
         stage ( ' Download Java code ') {
            steps{
                git branch: 'main', credentialsId: 'git-repo-creds', url: 'git@github.com:Shekhar9897/shekqwe.git'
      }
   }
    stage('Compiling and Running Test Cases') {
       steps {
              sh 'mvn clean'
           	  sh 'mvn compile'
              sh 'mvn test'
       }
}

  }
}

