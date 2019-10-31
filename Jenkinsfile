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
	 
	 
	 }





}