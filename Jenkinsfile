pipeline {

   agent any
   
     stages {
	 
	      stage('Build') {
		      steps {
			      bat label: '', script: 'mvn clean package'
			  }
		      post {
			     sucess {
				      echo 'archiving the artifacts'
					  archiveArtifacts '**/*.war'
				 }
				 failure {
				       echo 'failed to archive'
				 }
		  
		      }
		  }
	 
	 
	 }





}