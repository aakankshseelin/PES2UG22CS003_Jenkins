pipeline {
    agent any  // Use any available Jenkins agent
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o hello_exec hello.cpp'  // Compiles hello.cpp
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './hello_exec'  // Runs the compiled program
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying application...'
                }
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed'  // Displays message if any stage fails
        }
    }
}
