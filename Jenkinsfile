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
        // stage('quality gate'){
        //     steps{
        //         def qualitygate = waitForQualityGate()
        //         if (qualitygate.status != "OK") {
        //             error "Pipeline aborted due to quality gate coverage failure: ${qualitygate.status}"
        //         }
        //     }
        // }
    }
}