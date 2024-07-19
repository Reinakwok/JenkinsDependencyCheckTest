pipeline {
	agent any
	stages {

		stage('OWASP DependencyCheck') {
			steps {
				bat 'dependency-check.bat --format HTML --format XML'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}