pipeline {
    agent {
        label 'master'
    }
    stages {
              
        stage('Test') {            
            steps {                
                echo 'Testing'            
            }        
        }
        stage('Deploy - Staging') {            
            steps {                
                withMaven(maven: 'maven') {
                    sh "mvn clean package"
                }     
            }        
        }
        stage('Deploy - Staging1') {            
            steps {                
                docker run -d --name test3 10.186.122.166:5000/centos7-oracle-jdk7
              
            }        
        } 
    }
    post {        
        always {            
            echo 'One way or another, I have finished'            
        }        
        success {            
            echo 'I succeeeded!'        
        }        
        unstable {            
            echo 'I am unstable :/'        
        }        
        failure {            
            echo 'I failed :('        
        }        
        changed {            
            echo 'Things were different before...'        
        }    
    }
}