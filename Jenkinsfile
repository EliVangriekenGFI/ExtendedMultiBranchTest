pipeline {
    agent any
	environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Here we can build the project"'
				sh 'echo The "current build is"'
            }
        }
		stage('Test'){
			steps{
				sh 'echo "Here we can run some tests"'
			}
		}
    }
}
