pipeline {
	agent any

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	
	stages{

		stage('Checkout') {
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
				echo "JOB_NAME - $env.JOB_NAME"
			}
		}
		stage('Compile') {
			steps{
				sh 'mvn clean compile'
			}
		}
		stage('Test') {
			steps{
				sh 'mvn test'
			}
		}
		stage('Integration Test') {
			steps{
				echo "failsafe:integration-test failsafe:verify"
			}
		}

	}
	post{
		always{
			echo "I always run, I'm awesome."
		}
		success{
			echo "I run when you are successfull"
		}
		failure{
			echo "I run when you fail"
		}
	}

	
}
