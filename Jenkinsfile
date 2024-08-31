pipeline {
	agent {docker {image 'maven:3.9.9-amazoncorretto-17-al2023'}}
	
	stages{

		stage('Build') {
			steps{
				sh 'mvn --version'
				echo "Build"
			}
		}
		stage('Test') {
			steps{
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps{
				echo "Integration Test"
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
