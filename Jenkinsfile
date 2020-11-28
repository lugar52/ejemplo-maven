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
         stage('run_jar'){
            steps {
                dir("C:\\Users\\Luis Garrido\\Documents\\DevOps\\M4\\tarea\\ejemplo-maven") {
                    bat 'start mvnw.cmd spring-boot:run'
                }
            }
        }
    }
}
