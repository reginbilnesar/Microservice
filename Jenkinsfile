pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    // Authenticate and build Docker image
                    withDockerRegistry(credentialsId: 'docker-cred', url: 'https://index.docker.io/v1/') {
                        sh 'docker build -t reginbilnesar/emailservice:latest .'
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    // Authenticate and push Docker image
                    withDockerRegistry(credentialsId: 'docker-cred', url: 'https://index.docker.io/v1/') {
                        sh 'docker push reginbilnesar/emailservice:latest'
                    }
                }
            }
        }
    }
}
