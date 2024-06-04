pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t roopak1991/Microservice_Project:productcatalogservice_${BUILD_NUMBER}.0 ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push roopak1991/Microservice_Project:productcatalogservice_${BUILD_NUMBER}.0"
                    }
                }
            }
        }
    }
}
