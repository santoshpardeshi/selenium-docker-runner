pipeline {
	agent any
	stages {
		stage("Pull latest selenium-docker") {
			steps {
				sh "docker pull skpardeshi/selenium-docker"
			}
		}
		stage("Start hub") {
			steps {
				sh "docker-compose up --no-color -d hub chrome firefox"
			}
		}
		stage("Run Test") {
			steps {
				sh "docker-compose up search-module book-flight-module"
			}
		}
	}
	post {
		always {
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
		}
	}
}