pipeline {
    agent any    
    stages {
        stage('Hello') {
            steps {
                sh 'sh test.sh'
                echo env.BRANCH_NAME
            }
        }
    }
}
