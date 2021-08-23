pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/Harry061196/jenkinstest.git'
                bat 'mvn clean compile'
            }
        }
    }
}
