pipeline{
  agent any 
  stages {
    stage("code build") {
      steps {
         echo "this is code build"
        
      }
    }
      stage("build"){
        steps {
        echo "this is the maven"
        }
      }

      stage("this is deploying"){
      steps{
          echo "deploy application"
	  }

      
    }
	  
	  stage ("tomcat war file deploy"){
		  steps{
		  echo "deploing war file"
		  }
	  }
  }
}
