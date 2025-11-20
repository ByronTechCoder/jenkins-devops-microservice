
pipeline {
	agent { docker { image 'maven:3.8.1-jdk-11' args '-v /var/run/docker.sock:/var/run/docker.sock' } }
	environment {
		DOCKER_HOST = 'unix:///var/run/docker.sock'
	}
	stages {
		stage('Prepare') {
			steps {
				sh '''
				set -e
				# Install docker CLI in the agent if it's not present (Debian-based maven image)
				if ! command -v docker >/dev/null 2>&1; then
				  echo "Installing docker client inside agent..."
				  apt-get update && apt-get install -y docker.io || true
				fi
				docker --version || true
				'''
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