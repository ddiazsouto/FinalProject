pipeline{
    agent any
        environment {
        AWS_ACCESS_KEY_ID = credentials('ACCESS_KEY')
        AWS_SECRET_ACCESS_KEY = credentials('SECRET_ACCESS_KEY')
    }
    tools {
        maven 'Maven 3.6.3'
        jdk 'jdk9'
        nodejs 'node 15.11'
    }
    stages {
        stage('Test Backend') {
            steps {
                script {
                        sh 'bash jenkins/test-backend.sh'
                }
            }
        }
        stage('Test Frontend') {
            steps {
                script {
                    nodejs(nodeJSInstallationName: 'node 15.11') {
                        sh 'bash jenkins/test-frontend.sh'
                    }
                }
            }
        }
       stage('Deploy') {
            steps {
                script {
                        sh 'bash jenkins/deploy.sh'
                }
            }
        }
    }
}