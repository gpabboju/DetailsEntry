
pipeline {
    agent{
        label 'node1'
    }
   stages {
       stage('checkout') {
        steps{
	     git credentialsId: 'git_credentials', url: 'git@github.com:gpabboju/DetailsEntry.git'       
            } 
       }  // end of checkout stage
      stage('build') {
        steps{
          withMaven(mavenSettingsConfig:'b1adc66a-b1e8-4229-acee-f9de4803b6bf')   // //Config file provider and Pipeline maven Integration plugin needs to be installed
            sh 'mv clean package'
        }  
      }
      stage ('Deploy to Nexus') {
          withMaven(mavenSettingsConfig:'b1adc66a-b1e8-4229-acee-f9de4803b6bf')   // //Config file provider and Pipeline maven Integration plugin needs to be installed
          sh 'mv deploy'
        } // end of Deploy to Nexus stage
   } // end of stages
 
} // end of pipeline
