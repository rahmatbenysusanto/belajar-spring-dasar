pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Start Build'
                sh('./mvnw clean compile test-compile')
                echo 'Finish Build'
                node {
                    def remote = [:]
                    remote.name = 'test'
                    remote.host = 'test.domain.com'
                    remote.user = 'root'
                    remote.password = 'password'
                    remote.allowAnyHosts = true
                    stage('Remote SSH') {
                        sshCommand remote: remote, command: "ls -lrt"
                        sshCommand remote: remote, command: "for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done"
                    }
                }
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