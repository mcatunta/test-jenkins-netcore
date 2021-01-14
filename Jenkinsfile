pipeline {
    agent {
        docker {
            label 'windows'
            image 'mcr.microsoft.com/dotnet/core/sdk:3.1'            
            args '-p 3000:80 --mount src=${env.WORKSPACE}/test-jenkins-netcore_master,dst=/bld,type=bind'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Restore Packages') {
            steps {
                bat "dotnet restore TodoApi.csproj"
            }
        }        
        stage('Build') {
            steps {
                bat "dotnet build TodoApi.csproj --configuration Release"
            }
        }        
    }
}