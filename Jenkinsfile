pipeline {
    agent any 
    stages {
        stage('Pull script') { 
            steps {
                git url: 'https://github.com/Android60/get_response', branch: 'main'
            }
        }
        stage('Run script') { 
            steps {
                sh "chmod +x ./get_response.sh"
                catchError(buildResult: 'FAILURE', stageResult: 'FAILURE') {
                  sh "./get_response.sh https://www.google.com"
                }
            }
        }
    }
}
