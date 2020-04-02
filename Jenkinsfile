pipeline {
	agent any
	stages {
		stage("Parallel Execution") {
			steps {
				parallel(
				      a: {
					echo "mvn clean"
				      },
				      b: {
					echo "mvn test"
				      },
				      c: {
					echo "mvn package"
				      }
				)
			}
		}
		
		stage("Email Build Status"){
			steps {
				mail body: "${env.JOB_NAME}  - Build # ${env.BUILD_NUMBER}  - ${currentBuild.currentResult} \n\nCheck console output at ${env.BUILD_URL} to view the results.", subject: "${env.JOB_NAME}  - Build # ${env.BUILD_NUMBER}  - ${currentBuild.currentResult}!!", to: 'vinothsiva@gmail.com'
			}
		}
	}
}
