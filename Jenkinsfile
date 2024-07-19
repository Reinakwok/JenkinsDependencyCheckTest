pipeline {
    agent any
    environment {
        NVD_API_KEY = credentials('NVD-API-KEY')
    }
    stages {
        // stage('Checkout SCM') {
        //     steps {
        //         git url: 'https://github.com/ElizabethLanyl/SSD-lab06-jenkinsowasp.git', branch: 'master', credentialsId: 'jenkins-PAT'
        //     }
        // }
        stage('OWASP DependencyCheck') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML --nvdApiKey %NVD_API_KEY%', odcInstallation: 'owasp'
            }
        }
    }
    post {
        success {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}