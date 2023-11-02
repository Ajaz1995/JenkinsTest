pipeline {
    agent any
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac HelloWorld.java'
                sh 'jar cfm HelloWorld.jar Manifest.txt HelloWorld.class'
                sh 'mv HelloWorld.jar /home/ajaz/Firstbuild/JenkinsTest/HelloWorld.jar'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'i’m on stage 2'
            }
        }
        stage('Execute HelloWorld') {
            steps {
                sh 'cp /home/ajaz/Firstbuild/JenkinsTest/HelloWorld.jar .'
                sh 'java -jar HelloWorld.jar'
            }
         }
     }
        post {
        success {
            archiveArtifacts artifacts: 'HelloWorld.jar'
            
            }
        }
    }
