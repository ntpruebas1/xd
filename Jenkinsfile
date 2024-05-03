pipeline{
    agent any
    stages{
        stage('scan'){
            steps{
                dir('proy1'){
                    withSonarQubeEnv(installationName:'sq1'){
                        bat 'mvn clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
                    }
                    def qualitygate = waitForQualityGate abortPipeline: false
                    echo "${qualitygate.status}"
                }
            }
        }
    }
}