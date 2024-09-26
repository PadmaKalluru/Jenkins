pipeline{
	//agent any
	agent { dockerContainer { image 'maven:3.6.3'}}
	stages{
		stage('Build'){
			steps{
			      sh 'mvn --version'
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
			echo 'I run when your Successfull'
		}
		failure{
			echo 'failure'
		}
	}
}		
