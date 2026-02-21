pipeline{
    agent any
    stages{
        stage("Restore dependencies"){
             when {
					expression {
						return env.GIT_BRANCH == 'origin/main'
						}
				}
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build the app"){
             when {
					expression {
						return env.GIT_BRANCH == 'origin/main'
						}
				}
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Test the app"){
             when {
					expression {
						return env.GIT_BRANCH == 'origin/main'
						}
				}
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}