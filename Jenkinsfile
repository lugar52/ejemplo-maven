pipeline {
    agent any
    stages {
        stage('compile_code'){
            steps {
                dir("C:\\Users\\Luis Garrido\\Documents\\DevOps\\M4\\tarea\\ejemplo-maven") {
                    bat './mvnw.cmd clean compile -e'
                }
            }
        }
        stage('test_code'){
            steps {
                dir("C:\\Users\\Luis Garrido\\Documents\\DevOps\\M4\\tarea\\ejemplo-maven") {
                    bat './mvnw.cmd clean test -e'
                }
            }
        }
        stage('jar_code'){
            steps {
                dir("C:\\Users\\Luis Garrido\\Documents\\DevOps\\M4\\tarea\\ejemplo-maven") {
                    bat './mvnw.cmd clean package -e'
                }
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
         stage('run_jar'){
            steps {
                dir("C:\\Users\\Luis Garrido\\Documents\\DevOps\\M4\\tarea\\ejemplo-maven") {
                    bat 'start mvnw.cmd spring-boot:run'
                }
            }
        }
    }
}
