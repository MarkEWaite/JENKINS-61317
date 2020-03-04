#!groovy

@Library("jenlib@jenkins-lib") _

pipeline {
    agent any

    options
	{
		timestamps()
	}

    stages {
        stage('Prepare') {
            steps {
                script {
                    echo "stage 1"
                    echo "GIT COMMIT : ${env.GIT_COMMIT}"
                    echo "GIT BRANCH : ${env.GIT_BRANCH}"
                    echo sh(script: "env | sort", returnStdout: true) 

                    util.SayHello()
                }
            }
        }
    }
}
