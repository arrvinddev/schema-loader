pipeline {
    agent {
        node {
            label 'workstation'
        }
    }
    stages {
        stage('Build Docker image') {
            steps {
                sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 119876270834.dkr.ecr.us-east-1.amazonaws.com'
                sh 'docker build -t 119876270834.dkr.ecr.us-east-1.amazonaws.com/schema-loader:latest .'
                sh 'docker push 119876270834.dkr.ecr.us-east-1.amazonaws.com/schema-loader:latest'
            }
        }
    }
}