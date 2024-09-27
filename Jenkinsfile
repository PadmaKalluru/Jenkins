pipeline{
	agent any
	//agent{}
	stages{
		stage('Build'){
			steps{
				echo 'Build'
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
