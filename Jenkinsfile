pipeline{
    agent any
    stages{
        stage("Restoring dpendencies"){
            when {
                expression {
                    env.BRANCH_NAME == "main"
                }
            }
            steps{
                sh "dotnet restore"
            }
        }
        stage("Building the project"){
            when {
                expression {
                    env.BRANCH_NAME == "main"
                }
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }
        stage("Run the tests"){
            when {
                expression {
                    env.BRANCH_NAME == "main"
                }
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}