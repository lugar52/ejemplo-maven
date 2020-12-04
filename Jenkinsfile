pipeline {
    agent any
    stages{
        stage('package'){
            steps{
                bat 'mvn clean package -e'
            }
        }
        stage('sonarQube') {
            steps {
                withSonarQubeEnv(installationName: 'Sonar') 
                { // You can override the credential to be used
                    bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
                }
            }
        }
    }
}

