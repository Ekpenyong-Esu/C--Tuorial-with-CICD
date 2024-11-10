pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your repository
                git 'git@github.com:Ekpenyong-Esu/CSharpTuorial-with-CICD.git'
            }
        }
        stage('Restore Dependencies') {
            steps {
                // Restore NuGet packages
                script {
                    bat 'dotnet restore' // Use 'sh' instead of 'bat' if on Linux
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                // Add your build commands here
                sh 'make build
                // Build the project
                script {
                    bat 'dotnet build --configuration Release' // Use 'sh' for Linux
                }
            }
        }
        stage('Test') {
            steps {
                // Run tests
                script {
                    bat 'dotnet test' // Use 'sh' for Linux
                }
            }
        }
    }

    post {
        always {
            // Clean up workspace
            cleanWs()
        }
    }
}
