pipeline{
    agent any 

    tools {
        maven 'MAVEN_HOME'
        jdk 'JAVA_HOME'
    }
    stages{
        // step1
        stage('SCM') {
            steps{
                git 'https://github.com/gitadesh/Hello-World-Java.git'
            }
        }
        // step2 
        stage('build') {
            steps{
                sh 'mvn clean package'
            }
        }
    }    

}
