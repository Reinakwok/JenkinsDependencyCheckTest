pipeline {
    agent any
    // environment {
    //     NVD_API_KEY = credentials('nvd-api-key')
    // }
    stages {
        // stage('Checkout SCM') {
        //     steps {
        //         git url: 'https://github.com/ElizabethLanyl/SSD-lab06-jenkinsowasp.git', branch: 'master', credentialsId: 'jenkins-PAT'
        //     }
        // }
        stage('OWASP DependencyCheck') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'OWASP Dependency-Checke Vulnerabilities'
            }
        }
    }
    post {
        success {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}