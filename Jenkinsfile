pipeline {
    agent any 

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                // sh 'make' // Example of a shell command
            }
        }
        stage('Test') {
            steps {
                echo 'Running unit tests...'
                // sh 'make check'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // sh 'make publish'
            }
        }
    }
    
    post {
        always {
            echo 'This will always run, regardless of the outcome.'
        }
        success {
            echo 'The pipeline completed successfully!'
        }
        failure {
            echo 'The pipeline failed.'
        }
    }
}

