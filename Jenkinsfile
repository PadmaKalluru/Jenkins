pipeline{
	agent any
	//agent{}
	//environment{
		//mavenHome = tool 'myMaven'
		//PATH = "$mavenHome/bin:$PATH"
		
	stages{
		stage('Checkout'){
			steps{
				//sh 'mvn --version'
				echo 'Build'
				echo "$PATH"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_URL - $env.BUILD_URL"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
			}
		}
		//stage('Compile'){
		//	steps{
		//		sh "mvn clean compile"
		//	}
		//}	
		stage('Package'){
		        steps{
				    sh 'mvn package -DskipTests'
			}
		}
		stage('Build Docker Image'){
		       steps{
				script{
					dockerImage=docker.build("padmakalluru/jenkinsnew":$env.BUILD_ID)
				}
			   }
		}
		stage('Push Docker Image'){
			steps{
				script{
					docker.withRegistry('','dockerhub')
					dockerImage.push();
					dockerImage.push('latest');
				}
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
