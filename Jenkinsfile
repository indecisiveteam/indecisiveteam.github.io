pipeline{
	environment{
		BUILD_SCRIPTS_GIT="https://github.com/indecisiveteam/indecisiveteam.github.io.git"
		BUID_SCRIPTS='firstpipeline'
		BUILD_HOME='/var/lib/jenkins/workspace'
	}
	agent any
	stages{

		stage('Checkout'){
			steps{
				//sh "mkdir -p ${WORKSPACE}/repo;\
				//git clone ${BUILD_SCRIPTS_GIT} repo/${BUILD_SCRIPTS}"
				//sh "chmod -R +x ${WORKSPACE}/repo/${BUILD_SCRIPTS}"
			}
		}
	}	
}