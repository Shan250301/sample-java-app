pipeline {
	agent any

	tools {
		maven 'Maven 3.9.11'
		jdk 'Java21'
		git 'GitDefault'
	}
	
	stages {
		stage ('Checkout'){
			steps{
				git branch: 'main' , url: 'https://github.com/Shan250301/sample-java-app.git'
			}
		}
	stage('Test'){
		steps{
			bat 'mvn test'
		}
		post{
			always{
				junit 'target/surefire-reports/*.xml'
				}
			}
		}
	}
	post{
		success{
			echo ' Build and tests Passed!'
		}
failure{
	echo 'Build or tests failed. Check console output.'
}
}
}
