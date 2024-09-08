pipeline {
    agent any
    stages {
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