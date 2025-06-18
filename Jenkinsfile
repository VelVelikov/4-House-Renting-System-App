pipeline {
    agent any

    // environment {
    //     DOTNET_ROOT = '/usr/share/dotnet'  // adjust if needed
    // }

    // tools {
        // Only necessary if you're managing .NET SDK via Jenkins tools
        // dotnetsdk 'dotnet-8.0'
    // }

    stages {
        stage('Restore') {
            steps {
                echo 'Restoring NuGet packages...'
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }

    post {
        success {
            echo 'Build and test succeeded!'
        }
        failure {
            echo 'Build or test failed.'
        }
    }
}
