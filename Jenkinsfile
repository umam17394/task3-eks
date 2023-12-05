pipeline {
    agent any

    stages {
        stage('github clone') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/umam17394/devops-eks.git']])  
            }
        }
        stage('terraform init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('terraform validate') {
            steps {
                sh 'terraform validate'
            }
        }
        stage('terraform plan') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('terraform apply --auto-aprove') {
            steps {
                sh 'terraform apply'
            }
        }
        stage('terraform destroy') {
            steps {
                sh 'terraform destroy'
            }
        }
        
    }
}
