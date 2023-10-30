pipeline {
    agent any
    stages {
        stage('Build Java Project') {
            steps {
                // Assuming your Java file is named HelloWorld.java
                sh 'javac HelloWorld.java'
                sh 'jar cf HelloWorld.jar HelloWorld.class'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'i’m on stage 2'
            }
        }
        stage('Execute HelloWorld') {
            steps {
                // Copy the artifact to the desired location
                sh 'cp HelloWorld.jar D:/my app/HelloWorld.jar'
                // Execute the HelloWorld application
                sh 'java -jar D:/my app/HelloWorld.jar'
            }
        }
    }
    post {
        success {
            // Archive the artifact
            archiveArtifacts artifacts: 'HelloWorld.jar', fingerprint: true
        }
    }
}
