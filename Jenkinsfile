pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/pani-packer/aws']]])
            }
        }
        stage('Validate') {
            steps {
                sh '''
                packer validate aws_ec2.json
                '''
            }
        }
        stage('Build') {
            steps {
                sh '''
                packer build aws_ec2.json
                '''
            }
        }
    }
}
