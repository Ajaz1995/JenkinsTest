pipeline {
    agent any
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac HelloWorld.java'
                sh 'jar cf HelloWorld.jar HelloWorld.class'
                // Create the target directory if it doesn't exist
                sh 'mkdir -p /home/ajaz/Firstbuild'
                sh 'mv HelloWorld.jar /home/ajaz/Firstbuild'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'i’m on stage 2'
            }
        }
        stage('Execute HelloWorld') {
            steps {
                sh 'cp HelloWorld.jar /home/ajaz/Firstbuild/HelloWorld.jar'
                sh 'java -jar /home/ajaz/Firstbuild/HelloWorld.jar'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'HelloWorld.jar', fingerprint: true
        }
    }
}
