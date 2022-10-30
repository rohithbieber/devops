pipeline {
	agent any
	stages{
		stage ('fetch code'){
			steps {
				git branch:'vp-rem', url='https://github.com/devopshydclub/vprofile-repo.git' 
			}
		}	
		stage ('Build code') {
			steps {
				sh 'mvn install -DskipTests'
			}
			post {
				success {
					echo 'archiving....'
					archiveArtifacts artifacts: '**/target/*.war'
				}
			}
		}
		
		
	}
}
