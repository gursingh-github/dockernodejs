pipeline{
    agent any
    environment{
        DOCKERTAG = getDockerTag()
	registry = "gurpartapsingh88/k8simage"
	registryCredential = 'dockerhub'
    } 
    stages{
        stage("Build docker image"){
            steps{
	     	script{
		    docker.build registry + ":$BUILD_NUMBER"
		}
            } 
            
        }
    }
}

def getDockerTag(){
    def tag = sh script: 'git rev-parse HEAD', returnStdout: true
    return tag
}
