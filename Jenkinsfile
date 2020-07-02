pipeline{
    agent any
    environment{
        DOCKERTAG = getDockerTag()
    }
    stages{
        stage("Build docker image"){
            steps{
                sh "sudo docker build . -t gurpartapsingh88/nodejsk8s:v1 "
            }
            
        }
    }
}

def getDockerTag(){
    def tag = sh script: 'git rev-parse HEAD', returnStdout: true
    return tag
}
