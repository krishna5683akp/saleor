pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/krishna5683akp/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t madasu/saleor:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push madasu/saleor:DEV'
            }
        }
    }
}