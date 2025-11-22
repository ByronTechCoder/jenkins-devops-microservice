
pipeline {
	agent any 
	//agent {
		
		//docker {
			//image 'jenkins-maven-docker:latest'
			//args '-v /var/run/docker.sock:/var/run/docker.sock'
		//}
	//}
	environment {
	//	DOCKER_HOST = 'unix:///var/run/docker.sock'

	dockerHome = tool 'myDocker'
	mavenHome = tool 'myMaven'
	PATH = "$dockerHome/bin:$mavenHome/bin:$PATH}"
	}
	stages {

		stage('Build') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER $env.BUILD_NUMBER"
				echo "BUILD_ID $env.BUILD_ID"
				echo "BUILD_TAG $env.BUILD_TAG"
				echo "BUILD_URL $env.BUILD_URL"
			}
		}
		 stage('Test') {
			steps {
				echo "Test"
			}
		 }
		 stage('Integration Test') {
			steps {
				echo "Integration Test"
			}

		   
	 }
  	 } 
	 post {
		always {
			echo "This will always run"
		}
		success {
			echo "This will run only if successful"
		}
		failure {
			echo "This will run only if failed"
		}
	}
}