pipeline{
    agent any
    stages{
        stage('scan'){
            steps{
                dir('proy1'){
                    script{
                        bat 'mvn clean package'
                    }
                    withSonarQubeEnv(installationName:'sq1'){
                        bat 'mvn sonar:sonar'
                    }
                    script{
                        def qualitygate = waitForQualityGate abortPipeline: false
                        echo "${qualitygate.status}"
                    }
                }
            }
        }
    }
}