#!groovy

@Library("jenlib@jenkins-lib") _

pipeline {
    agent any

    options
	{
		timestamps()
	}

    enviroment {
        env.GIT_COMMIT_MINE = getCommitSha()
    }

    stages {
        stage('Prepare') {
            steps {
                script {
                    echo "stage 1"
                    echo "GIT COMMIT : ${env.GIT_COMMIT}"
                    echo "GIT BRANCH : ${env.GIT_BRANCH}"
                    // echo sh(script: "env | sort", returnStdout: true) 
                    echo "ACTURAL GIT COMMIT : ${env.GIT_COMMIT_MINE}"
                    util.SayHello()
                }
            }
        }
    }
}

def getCommitSha(){
    return sh(returnStdout: true, script: 'git rev-parse HEAD')
}