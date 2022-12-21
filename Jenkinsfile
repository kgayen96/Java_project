pipeline{
    agent any 
    stages{
        stage ("SonarQubeScanner") {
            steps {
                withSonarQubeEnv ("SonarQubeScanner") {
                sh "mvn sonar:sonar"
                }
            }
        }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-jenkins') {
                            sh 'chmod +x gradlew'
                            sh './gradlew sonarqube'
                    }
                }
            }
        }
    }
}

