pipeline {
    agent any
	
	parameters {
		booleanParam(defaultValue: false, description: 'Should I bump up the version', name: 'bumpVersion')
	}
	
	environment {
        CI = 'true'
    }
	
    stages {
        stage('Build') {
            steps {
                sh 'echo "Here we can build the project"'
				sh 'echo "The current build is:"'
				echo "flag: ${params.bumpVersion}"
            }
        }
		stage('Test'){
			steps{
				sh 'echo "Here we can run some tests"'
			}
		}
    }
}
