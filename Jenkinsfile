pipeline {
    agent any

    stages {
        stage('Maven package') {
                when{
                    branch 'develop'
                }
            steps {
                sh 'mvn clean package'
                }    
            }
            
        stage('Tomcat Deploy- dev') {
                when{
                    branch 'develop'
                }
            steps {
                echo " deploying to dev"
                } 
                }    
        stage('Tomcat Deploy- Prod') {
                when{
                    branch 'develop'
                }
            steps {
               echo "deploying to prod" 
                }    
            }
    }
}
