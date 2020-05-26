pipeline{
	agent any
	stages{
		stage("Run Test"){
			step{
				sh "docker-compose up"
			}
		}
		stage("Bring Grid Down"){
			step{
				sh "docker-compose down"
			}
		}
	}
}