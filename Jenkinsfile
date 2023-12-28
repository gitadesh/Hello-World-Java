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
        stage("build by maven"){
            steps{
                sh 'mvn clean install -DskipTests'
            }
            post{
                success{
                    archiveArtifacts artifacts: '**/target/*.*ar'
                }
            }
        }
        stage("unit test"){
            steps{
                sh 'mvn test'
            }
        }
        stage("integration test"){
            steps{
                sh 'mvn verify -DskipTests'
            }
        } 
        stage("code analysis with checkstyle"){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
            post{
                success{
                    echo 'generate analysis result'
                }
            }
        }
        stage('Push image to docker hub') {
            steps{
                //withCredentials([string(credentialsId: 'DOCKER_HUB_PASSWD', variable: 'DOCKER_HUB_PASS_CODE')]) {
                sh "sudo docker login -u hubadesh -p Adesh@12345 "
                sh "sudo docker push hubadesh/javaweb:${BUILD_TAG}"
            }
        }     
    }
}
