pipeline {  
    agent any  
        stages {  
            stage("git_checkout") {  
                    steps {  
                        sh '''
                       rm -rf maven-project
                    echo "cloning repository" 
                    git clone https://github.com/sivakiran95/maven-project.git
                    echo "repo cloned successfully"  
                     '''
                    }  
                    }

            stage('Build') {
                 steps {
                           sh '''
                         
                            cd maven-project
                            mvn  install
                           echo "mvn install successfully"
                            '''
                        }
                      }
            stage('Deployment') {
                      steps {
                            
                           sh '''
                            
                            cd /home/ubuntu/.jenkins/workspace/jenkins/maven-project/webapp
                            cp target/webapp.war /home/ubuntu/tomcat/apache-tomcat-9.0.78/webapps
                            '''                   
                            }
                 }      
        }
}

