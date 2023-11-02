pipeline {
    agent any
    stages {
        stage('Build Java Project') {
            steps {
                sh 'javac HelloWorld.java'
                sh 'jar cfm HelloWorld.jar Manifest.txt HelloWorld.class'
                sh 'rm -f /var/jenkins_home/HelloWorld.jar'
                //sh 'mv HelloWorld.jar /var/jenkins_home/HelloWorld.jar'/
                sh 'pwd'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'i’m on stage 2'
            }
        }
        stage('Execute HelloWorld') {
            steps {
                sh 'cp /var/jenkins_home/HelloWorld.jar .'
                sh 'java -jar HelloWorld.jar'
            
            }
          }
       }
    }
