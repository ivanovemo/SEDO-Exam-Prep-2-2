pipeline{
    agent any
    stages{
        stage("Restoring dpendencies"){
            when {
                expression {
                    return env.GIT_BRANCH == "origin/main"
                }
            }
            steps{
                sh "dotnet restore"
            }
        }
        stage("Building the project"){
            when {
                expression {
                    return env.GIT_BRANCH == "origin/main"
                }
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }
        stage("Run the tests"){
            when {
                expression {
                    return env.GIT_BRANCH == "origin/main"
                }
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}