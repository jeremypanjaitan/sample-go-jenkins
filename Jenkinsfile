// Run on an agent where we want to use Go
pipeline{
    agent any
    environment {
        root =  "/usr/local/go/bin/go"
        branch =  "master"
        scmUrl = "https://github.com/jeremypanjaitan/sample-go-jenkins.git"
    }
    stages{
        stage("Go Version"){
            steps{
                sh "${root} version"
            }
        }
        stage("Git Clone"){
            steps{
                git branch: "${branch}", url: "${scmUrl}"
            }
        }
        stage("Go Test"){
            steps{
                sh "${root} test ./... -cover"
            }
        }
    }
}