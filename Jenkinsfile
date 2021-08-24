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
                                FIRST_STRING = "${MAVEN_VERSIONS}".substring(MAVEN_VERSIONS.indexOf("The"),MAVEN_VERSIONS.indexOf("BUILD"))
                                echo "Git committer email: ${MAVEN_VERSIONS}"
                                echo "--------------------------${FIRST_STRING}"
                                REPLACE_STRINGS = FIRST_STRING.replaceAll("[INFO]","")
                                echo "${REPLACE_STRINGS}"
                                REPLACE_BRACE = REPLACE_STRINGS.replaceAll("[\\[\\]]", "")
                                echo "${REPLACE_BRACE}"
                                REPLACE_HYPHEN = REPLACE_BRACE.replaceAll("-","")
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
