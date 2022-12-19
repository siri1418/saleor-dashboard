pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/siri1418/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t siri1418/saleor-dashboar:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push siri1418/saleor-dashboar:DEV'
            }
        }
    }
}