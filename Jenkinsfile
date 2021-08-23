pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
//                 git 'https://github.com/Harry061196/jenkinstest.git'
                bat 'mvn clean compile'
            }
        }
        stage('Test'){
            steps{
                bat 'mvn clean test'
            }
        }
        stage('Versions'){
                    steps{
                        bat 'mvn versions:display-dependency-updates'
                    }
        }
        stage('JavaProgram'){
                            steps{
                                script{
                                    bat 'javac src/main/java/org/example/App.java'
                                    bat 'java src/main/java/org/example/App'
                                    }
                            }
                }

    }
}
