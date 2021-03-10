pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'echo Successful!'
                sh 'env'
            }
        }
    }
    post {
        always {
            echo 'always - This will always run'
        }
        success {
            echo 'success - This will run only if successful'
        }
        failure {
            echo 'failure - This will run only if failed'
        }
        unstable {
            echo 'unstable - This will run only if the run was marked as unstable'
        }
        changed {
            echo 'changed - This will run only if the state of the Pipeline has changed\nFor example, if the Pipeline was previously failing but is now successful'
        }
    }
}
