pipeline {
    agent any

    stages {
        stage('Stage 1') {
            steps {
                echo 'I’m on stage 1'
            }
        }

        stage('Stage 2') {
            steps {
                    catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                    echo 'I’m on stage 2'
                    exit 1
                }
            }
        }

        stage('Stage 3') {
            steps {
                echo 'I’m on stage 3'
            }
        }
    }
}
