pipeline {

   agent any
   
     stages {
	 
	      stage('Build') {
		      steps {
			      bat label: '', script: 'mvn clean package'
			  }
		      post {
			     success {
				      echo 'archiving the artifacts'
					  archiveArtifacts '**/*.war'
				 }
				 failure {
				       echo 'failed to archive'
				 }
		  
		      }
		  }
		  
		  stage('deploy to staging') {
		      steps {
                  build 'Deploy to Staging'              
			  }			  
		  
		  }
		  
		  stage('deploy to production') {
		      steps {
			      timeout(time: 1, unit: 'DAYS') {
                  input 'Approve deployment to production'
              }
			      build 'deploy to production'
			  }
		      post {
			     success {
				   echo 'deployment successful'
	  			 }
			     failure {
				   echo 'deployment failed'
				 }
			  }
		  
		  }
		  
	 
	 
	 }





}