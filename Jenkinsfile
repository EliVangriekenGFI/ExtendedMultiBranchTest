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
				script{
					if(params.bumpVersion == true){
						sh  './test.sh'
						sh  './bump-version-drynext.sh'
						sh  './bump-version.sh'
						sh	'echo "Version updated"'
					}else{
						sh	'echo "Version not updated"'
					}
				}
            }
        }
		stage('Test'){
			steps{
				sh 'echo "Here we can run some tests"'
			}
		}
    }
}
