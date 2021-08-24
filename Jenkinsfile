pipeline {
    agent any

    stages {
        stage('Versions'){
                    steps{
                    script {
                       MAVEN_VERSIONS = bat (
                            script: 'mvn versions:display-dependency-updates',
                            returnStdout: true
                        ).trim()
                        if("${MAVEN_VERSIONS}".contains("newer versions")){
                                MAVEN_VERSIONS = "${MAVEN_VERSIONS}".substring(MAVEN_VERSIONS.indexOf("The"),MAVEN_VERSIONS.indexOf("BUILD"))
                                echo "Git committer email: ${MAVEN_VERSIONS}"
                                echo "--------------------------${MAVEN_VERSIONS}"
                                MAVEN_VERSIONS = MAVEN_VERSIONS.replaceAll("[INFO]","")
                                echo "${MAVEN_VERSIONS}"
                                MAVEN_VERSIONS = MAVEN_VERSIONS.replaceAll("[\\[\\]]", "")
                                echo "${MAVEN_VERSIONS}"
                                MAVEN_VERSIONS = MAVEN_VERSIONS.replaceAll("--","")
                                echo "${MAVEN_VERSIONS}"
                        }
                        else{
                            echo "No Newer versions"
                        }
                       }
                    }
        }stage('Test'){
            echo "${MAVEN_VERSIONS}"
        }
    }
}
