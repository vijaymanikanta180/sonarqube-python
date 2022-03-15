pipeline{
    agent any
    stages{
        stage("SCM"){
            steps{
                git branch: 'master', url: 'https://github.com/vijaymanikanta180/sonarqube-python.git'
            }
        }
        stage("test in Sonarqube"){
            steps{
                withSonarQubeEnv(installationName: 'sonarqube', credentialsId: 'sonarqube token') {
                    sh "${ tool ("sonar-scanner")}/sonar-scanner \
                        -Dproject.settings=sonar-scanner.properties"
                }
            }
        }
    }
}
