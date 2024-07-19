pipeline {
    agent any
    environment {
        NVD_API_KEY = credentials('NVD_API_KEY')
    }
    stages {
        stage('OWASP DependencyCheck') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML --nvdApiKey %NVD_API_KEY% --nvdApiDelay 500', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
            }
        }
    }
    post {
        success {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}