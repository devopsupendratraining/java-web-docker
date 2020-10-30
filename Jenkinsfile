
pipeline{
  
 agent any
 
 tools{
   maven 'maven 3.6.3'
 }
  
  echo ${BUILD_NUMBER}
  stages{
  
    stage("Git Checkout"){
      steps{
        git credentialsId: '8081002c-b145-4930-89e6-6da5a0bb598d', url: 'https://github.com/devopsupendratraining/java-web-docker.git'
      }
    }
	
	stage("mvn build"){
			steps{
			  sh "mvn clean package"
			}
	
	}
    
    
  }
  
  
  
}
