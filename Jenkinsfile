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
                error 'Simulating a failure in stage 2'
            }
        }

        stage('Stage 3') {
            steps {
                echo 'I’m on stage 3'
            }
        }
    }
}
