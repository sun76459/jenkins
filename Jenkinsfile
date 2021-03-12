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
                subject: "Jenkins: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: """<p>${env.BUILD_STATUS}: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
                <p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>&QUOT;</p>""",
                to: "sun76459@gmail.com",
                attachLog: true
            )
        }
    }
}
