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
					      "pattern": "/home/ubuntu/indecisiveteam.github.io/Rakefile",
					      "target": "jenkins-new/git/"
					    },
					    {
					      "pattern": "/home/ubuntu/indecisiveteam.github.io/package.json",
					      "target": "jenkins-new/git/"
					    }
					]
					}"""

					def buildInfo = Artifactory.newBuildInfo()
					buildInfo.name = 'git-frog'
					buildInfo.number = 'v.0.0.2'
					server.publishBuildInfo buildInfo

					server.upload(uploadSpec)
				}			
			}
		}
	}
}
