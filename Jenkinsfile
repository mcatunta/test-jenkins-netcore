pipeline {
    agent {
        docker {
            image 'mcr.microsoft.com/dotnet/aspnet:3.1'
            args '-p 2002:80'
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
