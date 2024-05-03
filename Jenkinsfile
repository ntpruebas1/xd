pipeline{
    agent any
    stages{
        stage('scan'){
            steps{
                withSonarQubeEnv(installationName:'sq1'){
                    bat 'mvn clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
                }
                script{
                    def qualitygate = waitForQualityGate abortPipeline: false
                    echo "${qualitygate.status}"
                }
            }
        }
    }
}