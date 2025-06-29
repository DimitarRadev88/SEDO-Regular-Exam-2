pipeline {

    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout repo') {
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage("Build project") {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage("Run tests") {
            steps {
                bat 'dotnet test --no-build'
            }
        }

    }

}