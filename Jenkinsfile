pipeline{
    agent any
    stages{
        stage('Clean & Compile'){
            steps{
                sh "mvn clean compile"
            }
        }
        stage('test'){
            steps{
                sh "mvn test"
            }
            post {
                always {
                    junit allowEmptyResults: true,  testResults: "target/surefire-reports/*.xml"            
                }
            }
        }
        stage('Deploy'){
            steps{
                sh "mvn package"
            }
        }
        stage('Archiving'){
            steps{
                archiveArtifacts "**/target/*.jar"
            }
        }
    }
}
