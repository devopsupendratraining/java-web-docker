
pipeline{
  
 agent any
 
 tools{
   maven 'maven 3.6.3'
 }
  
  
  stages{
  
    stage("Git Checkout"){
      steps{
	      echo "${BUILD_NUMBER}"
        git credentialsId: '8081002c-b145-4930-89e6-6da5a0bb598d', url: 'https://github.com/devopsupendratraining/java-web-docker.git'
      }
    }
	
	stage("mvn build"){
			steps{
			  sh "mvn clean package"
			}
	}
	  
	  
	  stage("docker image build"){
			steps{
				sh "docker build -t  ragula001/javacocker:${BUILD_NUMBER} . "
			}
	}
	
	  stage("docker image push to docker rep"){
			steps{
			
				withCredentials([string(credentialsId: 'dock_hub_pwd', variable: 'docker_hub_pwd')]) {
					sh "docker login -u ragula001 -p ${docker_hub_pwd}"
				}
				sh "docker push ragula001/javacocker:${BUILD_NUMBER}"
			}
	}
	  
	  
	  
    
    
  }
  
  
  
}
