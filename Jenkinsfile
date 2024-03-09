pipeline {
    agent any
    
    stages {
        stage('Build') { 
            steps {
                script {
                    sh 'g++ -o output main.cpp'
                    build 'PES1UG21CS552-1'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    def output = sh(script: './output', returnStdout: true).trim()
                    echo "Output of main.cpp: ${output}"
                }
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
            error 'pipeline failed'
        }
    }
}
