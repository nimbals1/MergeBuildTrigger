node {
	  // Mark the code checkout 'stage'....
	  stage 'Stage Checkout'
	
	  // Checkout code from repository and update any submodules
	  checkout scm
	  sh 'git submodule update --init'  
	
	  stage 'Stage Build'
	//'sh './gradlew clean assembleRelease'
	'sh './gradlew clean build'
	stage 'test'
	sh './gradlew test'
	  //branch name from Jenkins environment variables
	  echo "My branch is: ${env.BRANCH_NAME}"
	 junit testResults: '**/surefire-reports/*.xml'
}
