pipeline {
    agent any 

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/Adithya-2008/-PES2UG22CS030_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES2UG22CS030-1'
                sh 'g++ main/hello.cpp -o output'  // Intentional error: Missing semicolon in hello.cpp
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
