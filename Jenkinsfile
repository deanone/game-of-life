// Powered by Infostretch 

timestamps {

node () {

	stage ('test-project-java-build - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'deanone_github_credentials', url: 'https://github.com/deanone/game-of-life.git']]]) 
	}
	stage ('test-project-java-build - Build') {
 			// Maven build step
	withMaven { 
 			if(isUnix()) {
 				sh "mvn compile " 
			} else { 
 				bat "mvn compile " 
			} 
 		} 
	}
	stage ('test-project-java-test - Build') {
 			// Maven build step
	withMaven { 
 			if(isUnix()) {
 				sh "mvn test " 
			} else { 
 				bat "mvn test " 
			} 
 		}
		// JUnit Results
		junit '**/target/surefire-reports/*.xml' 
	}
}
}