pipeline{
    agent any
    stages{
        stage('Clean & Compile'){
            steps{
		sh "printenv"
                sh "mvn clean compile"
            }
        }
        stage('test'){
            steps{
                sh "mvn test"
            }
        }
        stage('Deploy'){
            steps{
                sh "mvn package"
            }
        }
    }
}
