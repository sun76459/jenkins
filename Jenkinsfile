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
                sh 'df -h'
                sh 'pwd'
                sh 'ls -alF'
                sh 'git branch -a'
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
