pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building the application..."
                    sh "make -C main"
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo "Running tests..."
                    // Introducing an intentional error here
                    sh "cd /var/jenkins_home/workspace/PES2UG22CS256/main/ && ./hello_exec_nonexistent"
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo "Deploying application..."
                    sh 'echo "Deployment successful!"'
                }
            }
        }
    }
    post {
        failure {
            echo "Pipeline failed"
        }
        success {
            echo "Pipeline completed successfully!"
        }
    }
}