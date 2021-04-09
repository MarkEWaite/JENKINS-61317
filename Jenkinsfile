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
                    
                    util.SayHello()
                }
            }
        }
    }
}
