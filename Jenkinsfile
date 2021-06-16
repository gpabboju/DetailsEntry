pipeline {
  agent {
    label 'node1'
   }
  stages {
   stage('checkout'){
       steps{
         git credentialsId: 'git_credentials', url: 'git@github.com:gpabboju/DetailsEntry.git'
       }
    }
  stage('build') {
      steps{
        withMaven(mavenSettingsConfig:'b1adc66a-b1e8-4229-acee-f9de4803b6bf'){ //Config file provider and Pipeline maven Integration plugin needs to be installed.
         sh 'mvn clean package'}
     }
      
  }
   stage('Deploy to Nexus'){
      steps{
        withMaven(mavenSettingsConfig:'b1adc66a-b1e8-4229-acee-f9de4803b6bf'){
         sh 'mvn deploy'}
     }
    }
 }
}}
