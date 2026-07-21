@Library('Shared') _
pipeline{
    
    
    agent {label 'Don'}
    stages{
        stage('Hello'){
            steps{
                script{
                    hello()
                }
            }
        }
        stage('Code'){
            steps{
                script{
                    clone('https://github.com/Shub148/Django-notes-app.git','main')
                }
            }
        }
        stage('Build'){
            steps{
                script{
                    docker_build('notes-app','latest','Shub148')
                }
            }
        }
        stage('Push to docker hub'){
            steps{
                script{
                    docker_push('notes-app','latest','shub800')
                }
            }
        }
        stage('Deploy'){
            steps{
               echo 'This is deploying the code'
               sh 'docker compose up -d'
            
        }
        }
    }
}
