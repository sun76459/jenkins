pipeline {
    agent {
        docker { image 'node:14-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
                sh 'hostname'
                sh 'env'
                sh 'ip a'
                sh 'uptime'
                sh 'df -h'
                sh 'ls -alF'
                sh 'find .'
            }
        }
    }
    post {
        always {
            emailext (
                subject: '$DEFAULT_SUBJECT',
                body: '$DEFAULT_CONTENT',
                to: '$DEFAULT_RECIPIENTS',
                attachLog: true
            )
        }
    }
}
