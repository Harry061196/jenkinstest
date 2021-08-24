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
                                echo "--------------------------${FIRST_STRING}"
                                MAVEN_VERSIONS = MAVEN_VERSIONS.replaceAll("[INFO]","")
                                echo "${REPLACE_STRINGS}"
                                MAVEN_VERSIONS = MAVEN_VERSIONS.replaceAll("[\\[\\]]", "")
                                echo "${REPLACE_BRACE}"
                                MAVEN_VERSIONS = MAVEN_VERSIONS.replaceAll("-","")
                                echo "${REPLACE_HYPHEN}"
                        }
                        else{
                            echo "No Newer versions"
                        }
                       }
                    }
        }
    }
}
