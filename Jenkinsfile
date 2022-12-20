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

                    withSonarQubeEnv('sonar-server') {

                     sh 'mvn clean package sonar:sonar'
                 }
                }
            }
        }
    }
}
