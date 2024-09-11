pipeline{
    agent any
    tools{
        maven 'maven'
    
     }
     stages{
        stage("clone code"){
            steps{
              git credentialsId: 'git_credentials', url:'https://github.com/tejaswini9949/devops.git'
                
                
                            }


        }
        stage('Build'){

            steps{

                sh 'mvn clean package'
            }
            
            
        }
        stage('Deploy to tomcat server'){

            steps{
                
              sshagent(['tom']) {
                  
    sh "scp -v -o StrictHostKeyChecking=no target/vansro-1.0-SNAPSHOT.jar root@15.207.110.255:/opt/tomcat/webapps"
                }
               
            }
            
        }
        
     }
}

              
