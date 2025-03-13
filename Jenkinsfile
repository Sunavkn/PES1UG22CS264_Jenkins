pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/Sunavkn/PES1UG22CS264_Jenkins.git']]])
            }
        } 

        stage('Build') {
            steps {
                sh 'g++ -o PES1UG22CS264-1 main.cpp' 
            }
        }

        stage('Test') {
            steps {
                sh './PES1UG22CS264-1'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed' 
        }
    }
}
