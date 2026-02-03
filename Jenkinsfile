pipeline {
    agent any

    tools {
        jdk 'jdk17'
        maven 'maven3'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build & Test JAR') {
            steps {
                sh 'mvn clean test package'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar'
            echo 'Sample JAR built and archived successfully!'
        }
        failure {
            echo 'Build or test failed'
        }
    }
}


