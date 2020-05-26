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
				sh "docker-compose up search-module"
			}
		}
		stage("Run Book-Fligh Test") {
			steps {
				sh "docker-compose up book-flight-module"
			}
		}
		stage("Bring Grid Down") {
			steps {
				sh "docker-compose down"
			}
		}
	}
}