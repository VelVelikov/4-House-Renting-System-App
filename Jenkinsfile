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
        stage('Checkout the repository') {
            steps {
                checkout scm
            }
        }

        stage('Build the project') {
            steps {
                sh 'dotnet build'
            }
        }

        stage('Run tests') {
            steps {
                sh 'dotnet test'
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
