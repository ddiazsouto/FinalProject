pipeline {
    agent any
    stages{
        stage('0 - Configuration'){
            steps{
                sh 'bash jenkins/configuration.sh'
            }
        }
        stage('1 - Building'){
           steps{
               sh "docker-compose build"                                             
           }
       }
        stage('2 - Pushing to DockerHub'){
           steps{                                             
               sh "docker-compose push"
           }
       }
//        stage('Orchestration with Terraform'){
//            steps{
//                sh 'bash jenkins/orchestration.sh' 
//            }
//        }
//        stage('Deployment with Kubernetes'){
//            steps{                
//                sh 'bash jenkins/deploy.sh'
//            }                                            
//        }
    }
}
