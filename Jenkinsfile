pipeline{
	agent any
	//agent{}
	stages{
		stage('Build'){
			steps{
				echo 'Build'
				echo "$PATH"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_URL - $env.BUILD_URL"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
			}
		}
		stage('Test'){
			steps{
				echo 'Test'
			}
		}
	}
	post{
		always{
			echo 'Awesome'
		}
		success{
			echo 'I run when your Successful'
		}
		failure{
			echo 'failure'
		}
	}
}
