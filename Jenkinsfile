pipeline {
    agent any
    stages {
        stage('compile_code'){
            steps {
                    bat './mvnw.cmd clean compile -e'
            }
        }
        stage('test_code'){
            steps {
                    bat './mvnw.cmd clean test -e'
            }
        }
        stage('jar_code'){
            steps {
                    bat './mvnw.cmd clean package -e'
            }
        }
        stage('sonarQube') {
            steps {
                withSonarQubeEnv(installationName: 'Sonar-Server') 
                { 
                    bat 'mvnw org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
                }
            }
        }
         stage('run_jar'){
            steps {
                bat 'start mvnw.cmd spring-boot:run'
            }
        }
    }
}
