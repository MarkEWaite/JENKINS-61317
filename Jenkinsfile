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
                echo "stage 1"
                echo "GIT COMMIT : ${env.GIT_COMMIT}"
                
                util.SayHello()
            }
        }
    }
}
