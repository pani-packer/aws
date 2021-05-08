pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/pani-packer/aws']]])
            }
        }
        stage('Build') {
            steps {
                sh '''
                echo build
                '''
            }
        }
    }
}
