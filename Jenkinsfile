pipeline{
	agent any
	stages{
		
		stage("STart Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Running the test"){
			steps{
				bat "docker-compose up search-module1 book-flight-module1"
			}
		}
		
	}
	post {
		always{
		archiveArtifacts artifacts: 'output/**'
		bat "docker-compose down"
		
		}
	}
	
}