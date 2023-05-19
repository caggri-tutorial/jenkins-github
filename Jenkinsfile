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
        stage('deploy') {
            when {

                expression { params.ACTION == 'Proceed' }
            }
            steps {
                echo 'deploy'
            }
            
        }
    }
}
