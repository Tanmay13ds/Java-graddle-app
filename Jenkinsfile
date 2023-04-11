pipeline{
    agent any
    stages{
        stage("Sonar Quality check"){
            agent{
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonarqube') {
                        sh 'chmod +x gradlew'
                        sh "./gradlew build   |  tee output.log"
                    }
                }
            }
        }
    }
}
