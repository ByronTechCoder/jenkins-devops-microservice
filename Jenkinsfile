
pipeline {
	agent {
		docker {
			image 'jenkins-maven-docker:latest'
			args '-v /var/run/docker.sock:/var/run/docker.sock'
		}
	}
	environment {
		DOCKER_HOST = 'unix:///var/run/docker.sock'
	}
	stages {
		stage('Prepare') {
			steps {
				script {
					sh 'docker --version'
				}
			}
		}
		stage('Build') {
			steps {
				sh 'mvn --version'
				echo "Build"
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