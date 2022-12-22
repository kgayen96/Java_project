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
                    timeout(time: 1, unit: 'HOURS') {
                      def qg = waitForQualityGate()
                      if (qg.status != 'OK') {
                           error "Pipeline aborted due to quality gate failure: ${qg.status}
                      }
                    }
                }
            }
        }
    }
}
