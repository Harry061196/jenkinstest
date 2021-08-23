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
//                 git 'https://github.com/Harry061196/jenkinstest.git'
                bat 'mvn clean test'
            }
        }
        stage('Versions'){
                    steps{
//                         git 'https://github.com/Harry061196/jenkinstest.git'
                        bat 'mvn versions:display-dependency-updates'
                    }
        }
        stage('JavaProgram'){
                            steps{
//                                 git 'https://github.com/Harry061196/jenkinstest.git'
                                sh script 'javac src/main/java/org/example/App.java'
                                sh script 'java src/main/java/org/example/App'
                            }
                }

    }
}
