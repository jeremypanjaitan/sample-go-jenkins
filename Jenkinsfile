// Run on an agent where we want to use Go
pipeline{
    agent any
    environment {
        root =  "/usr/local/go/bin/go"
        branch =  "master"
        scmUrl = "https://github.com/jeremypanjaitan/sample-go-jenkins.git"
        dockerImageName = "sample-go-jenkins"
    }
    stages{
        stage("Docker build"){
            steps{
                sh "docker build -t ${dockerImageName} ."
            }
        }
        stage("Docker run"){
            steps{
                sh "docker run ${dockerImageName}"
            }
        }
    }
}