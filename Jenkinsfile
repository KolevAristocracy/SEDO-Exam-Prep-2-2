pipeline{
    agent any
    tools {
        dotnetsdk 'dotnet6'
    }
    stages{
        stage("Restore Dependencies"){
            when {
                AnyOf {
                    branch 'main'
                }
                
            }
            steps{
                sh "dotnet restore"
            }
        }

        stage("Build the app"){
            when {
                AnyOf {
                    branch 'main'
                }
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }
            
        stage("Run Tests"){
            when {
                AnyOf {
                    branch 'main'
                }
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}