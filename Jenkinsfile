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
                    script {
                       GIT_COMMIT_EMAIL = bat (
                            script: 'mvn versions:display-dependency-updates',
                            returnStdout: true
                        ).trim()
                        echo "Git committer email: ${GIT_COMMIT_EMAIL}"
                    }
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
