pipeline {
	agent any
	stages {
		stage("Clean Stage") {
			steps {
				bat "mvn clean"
				}
		}
		stage("Testing Stage") {
			steps {
				bat "mvn test"
				}
		}
		stage("Packaging Stage") {
			steps {
				bat "mvn package"
				}
		}
		stage("Email Build Status"){	
			steps {
				mail body: "${env.JOB_NAME}  - Build # ${env.BUILD_NUMBER}  - ${currentBuild.currentResult} \n\nCheck console output at ${env.BUILD_URL} to view the results.", subject: "${env.JOB_NAME}  - Build # ${env.BUILD_NUMBER}  - ${currentBuild.currentResult}!!", to: 'liujun19782053@gmail.com'
			}
		}
	}
}
