pipeline{

    agent any

    stages{

        stage('sonar quailty status'){

            agent{

                docker{
                    image 'maven'
                }
            }


            steps{

                script{

                    withSonarQubeEnv(credentialsId:'sonarqube') {

                        sh 'mvn clean package sonar:sonar'
    
                   }
                    
                }
            }
        }
    }
}
