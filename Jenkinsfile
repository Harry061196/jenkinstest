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
        stage('Versions'){
                    steps{
                        git 'https://github.com/Harry061196/jenkinstest.git'
                        bat 'mvn versions:display-dependency-updates'
                    }
        }
        stage('Java'){
                            steps{
                                git 'https://github.com/Harry061196/jenkinstest.git'
                                bat 'javac https://github.com/Harry061196/jenkinstest/blob/master/src/main/java/org/example/App.java'
                                bat 'java https://github.com/Harry061196/jenkinstest/blob/master/src/main/java/org/example/App.java'
                            }
                }

    }
}
