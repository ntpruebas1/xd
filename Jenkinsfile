pipeline{
    agent{any}
    stages{
        stage('scan'){
            steps{
                withSonarQubeEnv(installationName:'sq1'){
                    sh 'mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
                }
            }
        }
        stage('quality gate'){
            steps{
                timeout(time: 2, unit: 'MINUTES'){
                    waitForQualityGate abortPipeline true
                }
            }
        }
    }
}