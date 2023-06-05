pipeline {                                                                                                                                                                                                  
    agent any                                                                                                                                                                                               
    triggers {                                                                                                                                                                                              
        cron('H H(16-14) * * *')                                                                                                                                                                            
    }                                                                                                                                                                                                       
    tools {                                                                                                                                                                                                 
        jdk 'graalvm'                                                                                                                                                                                       
    }                                                                                                                                                                                                       
    stages {                                                                                                                                                                                                
        stage('Checkout') {                                                                                                                                                                                 
            steps {                                                                                                                                                                                         
                git branch: 'main', url: 'https://github.com/krepa-kamaleshvara/                                                                                                                            
devops_practical_test'                                                                                                                                                                                      
            }                                                                                                                                                                                               
        }                                                                                                                                                                                                   
        stage('Build') {                                                                                                                                                                                    
            steps {                                                                                                                                                                                         
                sh './mvnw compile quarkus:dev'                                                                                                                                                             
            }                                                                                                                                                                                               
        }                                                                                                                                                                                                   
        stage('Package') {                                                                                                                                                                                  
            steps {                                                                                                                                                                                         
                sh './mvnw package'                                                                                                                                                                         
            }                                                                                                                                                                                               
        }                                                                                                                                                                                                   
        post {                                                                                                                                                                                              
           always {                                                                                                                                                                                         
               deleteDir()                                                                                                                                                                                  
           }                                                                                                                                                                                                
        }                                                                                                                                                                                                   
     }                                                                                                                                                                                                      
}
