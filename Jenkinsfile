pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/Preetham0507/PES1UG21CS447_Jenkins']]])
            }
        }
        stage('Build') {
            steps {
                script {
                    build 'PES1UG21CS447-1'
                    sh 'g++ working.cpp -o output'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './output'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'Deployment steps go here'
                }
            }
        }
    }
    post {
        always {
            script {
                echo 'Pipeline completed'
            }
        }
        success {
            script {
                echo 'Pipeline succeeded'
            }
        }
        failure {
            script {
                echo 'Pipeline failed'
            }
        }
    }
}
