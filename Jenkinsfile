pipeline {
    agent {
        docker {
            alwaysPull true
            //image 'node:lts-buster-slim'
            image  maven:3.6.3-jdk-1
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true' 
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
    }
}
