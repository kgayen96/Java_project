pipeline{
    agent any 
    stages{
        stage ("sonar quality status"){
            
            agent{
                
                docker {
                    image 'maven'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonarqube-22') {
                     sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
}

