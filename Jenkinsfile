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
                        if("${GIT_COMMIT_EMAIL}".contains("older")){
                                echo "Git committer email: ${GIT_COMMIT_EMAIL}"
                            }
                            else{
                                echo "No new versions"
                            }
                        }
                  }
        }
    }
}
