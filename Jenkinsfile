pipeline {
    agent { label 'node-agent' }
    
    stages{
        stage('Code'){
            steps{
                git url: 'https://github.com/LondheShubham153/node-todo-cicd.git', branch: 'master' 
            }
        }
        stage('Build and Test'){
            steps{
                bat 'docker build . -t trainwithshubham/node-todo-test:latest'
            }
        }
        stage('Deploy'){
            steps{
                bat "docker-compose down && docker-compose up -d"
            }
        }
    }
}
