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
                withSonarQubeEnv('sonarqube') {
                    sh "${ tool ("sonarqube scanner")}/bin/sonar-scanner \
                        -Dproject.settings=sonar-scanner.properties"
                }
            }
        }
    }
}
