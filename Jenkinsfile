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
                git 'https://github.com/gitadesh/jenkins-training-CI-CD-Day6.git'
            }
        }
        // step2 
        stage('build') {
            steps{
                sh 'mvn clean package'
            }
        }
                // Step 3
        stage('Build docker image') {
                steps {
                    sh "sudo docker build -t hubadesh/myimage:${BUILD_NUMBER} ."
                }
        }
    }    

}
