pipeline{
    agent any
    tools {
        dotnetsdk 'dotnet6'
    }
    stages{
        stage("Restore Dependencies"){
            when {
                branch 'main'
            }
            steps{
                sh "dotnet restore"
            }
        }

        stage("Build the app"){
            when {
                branch 'main'
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }
            
        stage("Run Tests"){
            when {
                branch 'main'
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}