pipeline{
    agent any
    stages{
        stage('scan'){
            steps{
                withSonarQubeEnv(installationName:'sq1'){
                    bat 'mvn clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
                }
            }
        }
        stage("Quality gate") {
            steps {
                timeout(time: 3, unit: 'MINUTES') {
                    def qualitygate = waitForQualityGate()
                    echo "${qualitygate.status}"
                }
                echo "ASDASD"
            }
        }
    }
}