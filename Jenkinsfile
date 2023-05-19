pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Start Build'
                sh('./mvnw clean compile test-compile')
                sh('ssh root@167.71.200.180')
                sh('RahmatB12@s')
                echo 'Finish Build'
            }
        }
        stage('Test') {
            steps {
                echo 'Start Test'
                sh('./mvnw test')
                echo 'Finish Test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Hello Deploy'
            }
        }
    }

    post {
        always {
            echo 'Always'
        }
        success {
            echo 'Success'
        }
    }
}