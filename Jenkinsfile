pipeline {
    agent any
	environment {
        CI = 'true'
    }
	parameters {
		booleanParam(defaultValue: false, description: 'Should I bump up the version', name: 'bumpVersion')
	}
    stages {
        stage('Build') {
            steps {
                sh 'echo "Here we can build the project"'
				sh 'echo "The current build is:"'
				sh 'cat version.txt'
            }
        }
		stage('Test'){
			steps{
				sh 'echo "Here we can run some tests"'
			}
		}
    }
}
