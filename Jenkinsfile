pipeline {
	agent any
	// agent { docker {image 'maven:3.6.3'} }
	
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		path = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage ('Build') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
			}
		}
		stage ('Test') {
			steps {
				echo "Test"
			}
		}
		stage ('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	}

	post {
		always {
			echo 'Im awesome. I run always'
		}
		success {
			echo 'I run when when you are successful'
		}
		failure {
			echo 'I run when you are failed'
		}
	}
}
