pipeline {
    agent any    
    stages {
        stage('package') {
            steps {
                sh 'zip -r function.zip lambda_function.py'
                archiveArtifacts artifacts: 'function.zip', fingerprint: true
            }
        }
        stage('deploy') {
            steps {
                echo 'Lambda deploy stage - test branch'
            }
        }
    }
}
