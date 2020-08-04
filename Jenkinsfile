pipeline {
    agent any

    tools {
      maven 'Maven 3.6.3'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Compiling carts ...'
                sh 'mvn compile'
            }
            }

        stage('Test') {
            steps {
                echo 'Testing carts ...'
                sh 'mvn clean test'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging carts ...'
                sh 'mvn -DskipTests package'
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}