pipeline {
    agent any
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac HelloWorld.java'
                sh 'jar cvf HelloWorld.jar HelloWorld.class'
                sh 'mv HelloWorld.jar /var/jenkins_home/HelloWorld.jar'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'i’m on stage 2'
            }
        }
        stage('Execute HelloWorld') {
            steps {
                sh 'cp HelloWorld.jar /var/jenkins_home/HelloWorld.jar'
                sh 'java -jar /var/jenkins_home/HelloWorld.jar'
            }
         }
     }
        post {
        success {
            archiveArtifacts artifacts: 'HelloWorld.jar', fingerprint: true
            
            }
        }
    }
