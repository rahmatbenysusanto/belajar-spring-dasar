pipeline {
    agent any
    stages {
        stage('hello') {
            steps {
                echo 'Hallo Rahmat Beny'
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