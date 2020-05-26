pipeline {
	agent any
	stages {
		stage("Start hub") {
			steps {
				sh "docker-compose up --no-color -d hub chrome firefox"
			}
		}
		stage("Run Search Module Test") {
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