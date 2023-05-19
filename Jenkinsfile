pipeline {
    agent any  
    parameters {
        choice(
            choices: ['Proceed' , 'Yield'],
            description: 'Continiue process',
            name: 'ACTION')
    }  
    stages {
        stage('package') {
            steps {
                sh 'zip -r function.zip lambda_function.py'
                archiveArtifacts artifacts: 'function.zip', fingerprint: true
            }
        }
        stage ('deploy') {
            when {
                // Only say hello if a "greeting" is requested
                expression { params.ACTION == 'Proceed' }
            }
        }
    }
}
