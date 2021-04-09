#!groovy

library identifier: 'jenlib@jenkins-lib', retriever: modernSCM([$class: 'GitSCMSource', remote: 'https://github.com/MarkEWaite/JENKINS-61317', traits: [gitBranchDiscovery()]])

pipeline {
    agent any
    stages {
        stage('Use default checkout') {
            steps {
                script {
                    echo "stage 1"
                    echo "GIT COMMIT : ${env.GIT_COMMIT}"
                    echo "GIT BRANCH : ${env.GIT_BRANCH}"
                    if (env.GIT_COMMIT == 'a8c235b10c55e2f065293b1c1ad9b3bffd45d9d9') { // Library SHA-1
                        addWarningBadge id: 'bad-sha-1', text: 'Unexpected SHA-1 returned by checkout'
                        currentBuild.result = 'UNSTABLE'
                    }
                    
                    util.SayHello()
                }
            }
        }
    }
}
