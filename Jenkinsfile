pipeline {
    agent any
    tools{
        maven 'maven_3_6_3'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Klellis77/DevOps-Automation']])
                sh 'mvn clean install'
            }
        }
    }
}
