pipeline {
    agent any
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac HelloWorld.java'
                sh 'jar cf HelloWorld.jar HelloWorld.class'
                sh 'mv HelloWorld.jar https://github.com/Ajaz1995/JenkinsTest/blob/main/'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'i’m on stage 2'
            }
        }
        stage('Execute HelloWorld') {
            steps {
                sh 'cp HelloWorld.jar https://github.com/Ajaz1995/JenkinsTest/blob/main/HelloWorld.jar'
                sh 'java -jar https://github.com/Ajaz1995/JenkinsTest/blob/main/HelloWorld.jar'
            }
        }
    }
}
