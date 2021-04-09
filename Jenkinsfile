#!groovy

library identifier: 'jenlib@jenkins-lib', 
        retriever: modernSCM([$class: 'GitSCMSource', 
                              credentialsId: 'MarkEWaite-github-rsa-private-key', 
                              remote: 'git@github.com:MarkEWaite/JENKINS-61317.git', 
                              traits: [gitBranchDiscovery()]])

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
        stage('Use checkout') {
            steps {
                dir('a-subdir') {
                    script {
                        checkout([$class: 'GitSCM', 
                                  branches: [[name: '*/master-load-ssh-library']], 
                                  userRemoteConfigs: [
                                          [credentialsId: 'MarkEWaite-github-rsa-private-key', 
                                           url: 'git@github.com:MarkEWaite/JENKINS-61317.git']]])
                        echo "stage 2"
                        echo "GIT COMMIT : ${env.GIT_COMMIT}"
                        echo "GIT BRANCH : ${env.GIT_BRANCH}"
                    
                        util.SayHello()
                    }
                }
            }
        }
    }
}
