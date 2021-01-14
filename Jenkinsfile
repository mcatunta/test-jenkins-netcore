pipeline {
    agent {
        docker {
            image 'mcr.microsoft.com/dotnet/core/sdk:3.1'
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
