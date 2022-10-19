pipeline {
    agent any
    stages {
        stage('GIT') {
            steps {
               git branch: 'main', credentialsId: '3a76ac10-13dd-472f-b806-4640e6dbf006', url: 'https://github.com/thanhka/testjenkins.git' 
            }
        }    
        stage('DOCKER') {
            steps {
               withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t thanhgosu/testdocker:v10 .'
                    sh 'docker push thanhgosu/testdocker'           
               }
            }
        }
    }
}
