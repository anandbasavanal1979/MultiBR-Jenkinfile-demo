pipeline {
    agent any 
	stages {
	   stage("maven build") {
	       when {
		     branch "develop"
		   }
		   steps{
               sh "mvn package"    		   
		   }
	   }
		   
		   stage("sonarQube analysis"){
		         when {
				 branch "develop"
				 }
				 
				 steps{
				      withSonarQubeEnv("sonarQube"){
				      sh "mvn sonar:sonar"
				 }
		   }
		   }
		   
		   stage("sonarQube status"){
		         when {
				 branch "develop"
				 }
				 
				 steps{
				      timeout(time: 1,unit: 'HOURS'){
					  def qg = waitForQualityGate()
					  if (qg.status != 'OK')
					  {
					   error "pipeline aborted due to qualty gate failures : ${qg.status}"
					  }
				     
				 }
		   }
		   }  
		   stage("dep 2 Nexus"){
		        when {
				branch "develop"
				}
				steps{
				
				echo "deploying to nexus"
				     
				}
				
				}
				
				stage("dep QA"){
				   when {
				   branch "QA"
				   
				  }
				  
				  steps{
				  echo "deploy to QA"
				  }
				}
		   }
	   }
	
	

