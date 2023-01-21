pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/klellis77/devops-automation']]])
                sh 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t klellis77/devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   withCredentials([string(credentialsId: 'dockerhub-pwd', variable: 'LetsGoforit75}')]) {
                   sh 'docker login -u klellis77 -p ${LetsGoforit75}'

}
                   sh 'docker push klellis77/devops-integration'
                }
            }
        }
    }
}
