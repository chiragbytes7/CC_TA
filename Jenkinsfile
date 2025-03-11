pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '/main']],
                    userRemoteConfigs: [[url: 'https://github.com/chiragbytes7/PES1UG22CS161_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS161-1'
                sh 'g++ chirag.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
