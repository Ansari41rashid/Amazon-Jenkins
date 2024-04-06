pipeline {
   agent {
  label 'ssh-node'
}
    tools {
  maven 'mvn'
  git 'Default'
}
    stages {

        stage('pull') {
            steps {
                git branch: 'main', url: 'https://github.com/PraveenKuber/Amazon-Jenkins.git'
            }
        }
        
        stage('compile') {
            steps {
                bat 'mvn compile'
            }
          }
        
         stage('build') {
            steps {
               bat 'mvn clean install'
            }
        }
    }
    post{
       failure{
          echo "Failute in the build"
       }
    }
     
    }  
  
