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
					def server = Artifactory.server 'Artifactory Version 6.6.0'
					def uploadSpec = """{
					  "files": [
					    {
					      "pattern": "/home/ubuntu/lol.txt",
					      "target": "jenkins-new/lol/"
					    },
					    {
					      "pattern": "/home/ubuntu/lol1.txt",
					      "target": "jenkins-new/lol/"
					    },
					    {
					      "pattern": "/home/ubuntu/lol2.txt",
					      "target": "jenkins-new/lol/"
					    }
					]
					}"""

					def buildInfo = Artifactory.newBuildInfo()
					buildInfo.name = 'lol-frog'
					buildInfo.number = 'v.0.0.1'
					server.publishBuildInfo buildInfo

					server.upload(uploadSpec)
				}			
			}
		}
	}
}
