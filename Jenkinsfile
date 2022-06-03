pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
         stage('Clone repository') { 
            steps { 
                script{
                checkout scm
                }
            }
         }

        stage('Build') { 
            steps { 
                
                 sh''' sudo docker build -t flaskcompose . '''
                }
            }
        
        stage('Deploy') { 
            steps { 
                
                 sh''' sudo /usr/local/bin/docker-compose up -d '''
                }
            }
       }
   
   }
