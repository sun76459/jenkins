pipeline {
    agent {
        docker { image 'node:14-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
    post {
        always {
            emailext (
                subject: '$DEFAULT_SUBJECT',
                body: '$DEFAULT_CONTENT'
                mimeType: 'text/html',
                to: "sun76459@gmail.com",
                attachLog: true
            )
        }
    }
}
