pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                sh "ls"
                git branch:'main', url:'https://github.com/Pabsm94/course3-jenkins-gs-spring-petclinic.git'
                sh 'ls'
            }
        }
        stage('build'){
            steps {
                sh "./mvnw package"
            }
        }
        stage('capture'){
            steps{
                archiveArtifacts '**/target/*.jar'
                jacoco()
                junit stdioRetention: '', testResults: '**/target/surefire-reports/TEST*.xml'
            }
        }
    }
}