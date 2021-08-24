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
                       MAVEN_VERSIONS = bat (
                            script: 'mvn versions:display-dependency-updates',
                            returnStdout: true
                        ).trim()
                        if("${MAVEN_VERSIONS}".contains("newer versions")){
                                FIRST_STRING = "${MAVEN_VERSIONS}".substring(0,MAVEN_VERSIONS.length())
                                echo "Git committer email: ${MAVEN_VERSIONS}"
                                echo "--------------------------${FIRST_STRING}"
                        }
                        else{
                            echo "No Newer versions"
                        }
                       }
                    }
        }
    }
}
