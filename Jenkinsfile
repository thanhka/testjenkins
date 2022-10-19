pipeline {
    agent any
    stages {
        stage('Clone stage') {
            steps {
               git branch: 'masin', credentialsId: '3a76ac10-13dd-472f-b806-4640e6dbf006', url: 'https://github.com/thanhka/testjenkins.git' 
            }
        }    
        stage('Clone stages') {
            steps {
               withDockerRegistry(credentialsId: 'dockerhub', url: 'https://hub.docker.com/repository/docker/thanhgosu/testdocker') {
                    sh 'docker build -t thanhgosu/testdocker:v10 .'
                    sh 'docker push thanhgosu/testdocker'           
               }
            }
        }
    }
}
