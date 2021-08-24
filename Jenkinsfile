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

                            sh(returnStdout: true, script: "mvn versions:display-dependency-updates")
                            echo '----------------Newer versions Dependencies-------------------'

                    }
        }
        stage('JavaProgram'){
                            steps{
                                script{
                                    bat 'javac -cp . src/main/java/org/example/App.java'
                                    bat 'java -classpath ../../ org.example.App'
                                    }
                            }
                }

    }
}
