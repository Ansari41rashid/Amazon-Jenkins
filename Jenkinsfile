pipeline {
   agent {
  label 'Linux-slave1'
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
                sh 'mvn compile'
            }
          }
        
         stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }
    }
    post{
       failure{
          echo "Failute in the build"
       }
    }
     
    }  
  
