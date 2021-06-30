pipeline {
    agent { docker { image 'golang' } }
    stages {
        stage('build') {
            steps {
                sh 'df -h'
                sh 'pwd'
                sh 'go version'
            }
        }
    }
}
