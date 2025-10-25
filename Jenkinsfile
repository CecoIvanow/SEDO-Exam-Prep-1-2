pipeline {
    agent any
    stages {
        stage('Restore') {
            when { branch pattern: "(main|feature/.*)", comparator: "REGEXP"}
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Install dependencies') {
            when { branch pattern: "(main|feature/.*)", comparator: "REGEXP"}
            steps {
                bat 'dotnet build'
            }
        }
        stage('Test') {
            when { branch pattern: "(main|feature/.*)", comparator: "REGEXP"}
            steps {
                bat 'dotnet test'
            }
        }
    }
}