pipeline {
    agent any

    tools { 
      maven 'MAVEN_HOME' 
      jdk 'JAVA_HOME' 
    }
    
    stages {
        // Step 1
        stage('SCM') {
                steps {
                    git 'https://github.com/gitadesh/jenkins-training-CI-CD-Day6.git'
                }        
        }
        // Step 2
        stage('Build by Maven') {
                steps {
                    sh 'mvn clean package'
                }
        }

    }
    
}
        
