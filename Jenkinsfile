pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				'C:\Users\reina\Documents\SIT\Year2\Tri3\ICT2216 Secure Software Development\Labs\JenkinsDependencyCheckTest'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}