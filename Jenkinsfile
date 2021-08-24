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
                            def maven
                            maven = bat(returnStdout: true, script: "mvn versions:display-dependency-updates")
                            echo '----------------Newer versions Dependencies-------------------'
                            echo "${env.MAVEN}"
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
