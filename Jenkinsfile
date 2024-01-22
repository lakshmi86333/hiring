pipeline {
    agent any

    stages {
        stage('Maven package') {
            steps {
                when{
                    branch 'develop'
                }
                sh 'mvn clean package'
                }    
            }
            
        stage('Tomcat Deploy') {
            steps {
                when{
                    branch 'develop'
                }
                sshagent(['tomcat']) {
                sh "scp –o StrictHostKeyChecking=no target/*.war ec2-user@172.31.30.183:/opt/tomcat8/webapps"
                sh "ssh ec2-user@172.31.30.183 /opt/tomcat8/bin/shutdown.sh "
                sh "ssh ec2-user@172.31.30.183 /opt/tomcat8/bin/startup.sh "
                } 
                }    
            }   
    }
}
