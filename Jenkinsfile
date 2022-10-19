pipeline {
    agent any
    stages {
        stage('Clone stage') {
            steps {
               git branch: 'main', credentialsId: 'testjenkinsgitlab', url: 'https://gitlab.com/thanhka/testjenkinsgitlab.git' 
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
