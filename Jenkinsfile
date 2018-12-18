pipeline{
	environment{
		BUILD_SCRIPTS_GIT="https://github.com/indecisiveteam/indecisiveteam.github.io.git"
		BUILD_SCRIPTS='firstpipeline'
		BUILD_HOME='/var/lib/jenkins/workspace'
	}
	agent any
	stages{

		stage('Checkout'){
			steps{
				//sh "echo 123" 
				script{
					def server = Artifactory.server 'Artifactory Version 6.5.13'
					def uploadSpec = """{
					  "files": [
					    {
					      "pattern": "/home/ubuntu/lol.txt",
					      "target": "jenkins-new/3/"
					    }
					]
					}"""

					def buildInfo = Artifactory.newBuildInfo()
					buildInfo.name = 'super-frog'
					buildInfo.number = 'v1.2.3'
					server.publishBuildInfo buildInfo

					server.upload(uploadSpec)
				}			
			}
		}
	}
}
