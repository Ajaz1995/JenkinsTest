pipeline {
    agent any
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac HelloWorld.java'
                sh 'jar cf HelloWorld.jar HelloWorld.class'
                sh 'mv HelloWorld.jar /home/ajaz/Firstbuild/JenkinsTest/.git'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'i’m on stage 2'
            }
        }
        stage('Execute HelloWorld') {
            steps {
                sh 'cp HelloWorld.jar /home/ajaz/Firstbuild/JenkinsTest/.git/HelloWorld.jar'
                sh 'java -jar /home/ajaz/Firstbuild/JenkinsTest/.git/HelloWorld.jar'
            }
        }
    }
}
