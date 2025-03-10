pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o main/hello_exec main/hello.cpp'  // Compile hello.cpp
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './main/non_existent_file'  // Intentional error: File does not exist
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
            echo 'Pipeline failed'  // Error message when pipeline fails
        }
    }
}
