pipeline {
    agent any
	
    stages {
        stage('Stage 1') {
   	    steps {
        	 sh 'javac HelloWorld.java'
       		 sh 'jar cf helloworld.jar HelloWorld.class'
       		 sh 'mv helloworld.jar /home/ajaz/JenkinsTest'
    	}
    }

        stage('Stage 2') {
            steps {
                echo 'I’m on stage 2'
            }
        }

        stage('Stage 3') {
    steps {
        // Pull the artifact
        sh 'cp /home/ajaz/JenkinsTest/helloworld.jar .'
        // Execute the application
        sh 'java -jar helloworld.jar'
  	  }
	}
    }
}
