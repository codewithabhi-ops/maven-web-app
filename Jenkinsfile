pipeline {  

    agent any
        
   
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/codewithabhi-ops/maven-web-app.git'
            }
        }
         stage('build'){
             steps{
                 sh 'mvn clean package'
             }
         }
         stage('sonarqube'){
             steps{
               withSonarQubeEnv('mySonarQube-9') {
                    sh 'mvn sonar:sonar'

                }
             }
         }
        
    }
}
