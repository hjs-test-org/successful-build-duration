pipeline {
    agent any 

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running unit tests...'
            }
        }
        stage('Registering build artifact') {
            steps {
                script {
                    echo 'Registering the metadata'
                    def artifactId = registerBuildArtifactMetadata(
                        name: "My Playground",
                        version: "1.0.0",
                        type: "docker",
                        url: "http://localhost:9002",
                        digest: "3x789064707039346163693930",
                        label: "PreProd"
                    )
                    echo "Artifact Id is: ${artifactId}"
                    env.ARTIFACT_ID = artifactId
                    sleep 3
                }
            }
        }
         stage('Deploy') {
            steps {
                echo 'Deploying the application...'
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

