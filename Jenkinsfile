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
						sh	'git checkout master'
						sh	'git pull origin master'
						sh  './test.sh && echo "next line"'
						sh 	'nextVersion=$(./bump-version-drynext.sh)'
						sh	'echo $nextVersion'
						sh  './bump-version.sh $nextVersion'
						sh	'git add version.txt'
						sh	'git commit -m "updated version number"'
						sh 	'git push'
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
