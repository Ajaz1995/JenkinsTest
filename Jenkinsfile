pipeline {
    agent any
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac HelloWorld.java'
                sh 'jar cf HelloWorld.jar HelloWorld.class'
                sh 'mkdir -p /home/ajaz/Firstbuild/JenkinsTest'
                sh 'mv HelloWorld.jar /home/ajaz/Firstbuild/JenkinsTest'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'i’m on stage 2'
            }
        }
        stage('Execute HelloWorld') {
            steps {
                sh 'cp HelloWorld.jar /home/ajaz/Firstbuild/JenkinsTest/HelloWorld.jar'
                sh 'java -jar /home/ajaz/Firstbuild/JenkinsTest/HelloWorld.jar'
            }
         }
        
        post {
        success {
            archiveArtifacts artifacts: 'HelloWorld.jar', fingerprint: true
            
            }
        }
    }
}
