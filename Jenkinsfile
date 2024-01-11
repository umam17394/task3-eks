pipeline {
    agent any

    stages {
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
        stage('terraform apply') {
            steps {
                sh 'terraform apply --auto-approve'
            }
        }
        stage('terraform destroy') {
            steps {
                sh 'terraform destroy --auto-approve'
            }
        }
        
    }
}
