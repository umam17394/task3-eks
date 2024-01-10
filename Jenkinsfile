pipeline {
    agent any

    stages {
        stage('aws cred') {
            steps {
               withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
                    credentialsId: "aws-cred",
                    accessKeyVariable: 'AWS_ACCESS_KEY_ID',
                    secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                    sh 'aws ec2 describe-instance'
                }
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
        /* stage('terraform apply --auto-approve') {
            steps {
                sh 'terraform apply --auto-approve'
            }
        } */
        stage('terraform destroy --auto-approve') {
            steps {
                sh 'terraform destroy --auto-approve'
            }
        }
        
    }
}
