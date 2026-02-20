pipeline{
    agent any
    stages{
        stage("Restoring dpendencies"){
            when {
                branch "main"
            }
            steps{
                sh "dotnet restore"
            }
        }
        stage("Building the project"){
            when {
                branch "main"
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }
        stage("Run the tests"){
            when {
                branch "main"
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}