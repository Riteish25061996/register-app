pipeline {
	agent { label 'jenkins-agent' }
	tools {
		jdk 'java21'
		maven 'Maven3'
	}
	
	stages {
		stage("cleanup-workspace"){
				steps {
				    cleanWs()
				}
		}
		
		stage("git-checkout") {
				steps {
					git branch: 'main', credentialsId: 'github', url: 'https://github.com/Riteish25061996/register-app.git'
				}
		}
		
		stage("build-app") {
				steps {
					sh "mvn clean package"
				}
		
		}
		
		stage("mvn-test") {
				steps{
					sh "mvn test"
				}
		
		}
	
	}

}
