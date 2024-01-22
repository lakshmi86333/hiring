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
            
        stage('Tomcat Deploy- dev') {
            steps {
                when{
                    branch 'develop'
                }
                echo " deploying to dev"
                } 
                }    
            } 
        stage('Tomcat Deploy- Prod') {
            steps {
                when{
                    branch 'develop'
                }
               echo "deploying to prod" 
                }    
            }
    }
}
