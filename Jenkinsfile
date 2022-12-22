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
                     
                    }
                }
            }
        }
        stage('Quality Gate status'){
            steps{
                scripts{
                    waitForQualityGate abortPipeline: false, credentialsId: 'sonarqube-22'
                }
            }
        }
    }
}

