pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/Harry061196/jenkinstest.git'
                bat 'mvn clean compile'
            }
        }
        stage('Test'){
            steps{
                git 'https://github.com/Harry061196/jenkinstest.git'
                bat 'mvn clean test'
            }
        }
        stage('Test'){
                    steps{
                        git 'https://github.com/Harry061196/jenkinstest.git'
                        bat 'mvn versions:display-dependency-updates'
                    }
                }
    }
}
