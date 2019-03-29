pipeline {

    agent any 

    stages {

	stage("Build"){
	    steps{
		sh 'mvn clean package'
	    }
	    post{
		success{
		    echo 'Now Archiving ... ' 
		    archiveArtifacts artifacts: '**/*.war'
		}
	    }
	}

	stage("Deploy to stage"){
	     steps{
		 build job: 'deploy-to-stage'
	     }
	}

    }

}
