pipeline {
    agent none   // No default agent

    stages {

        stage('Checkout') {
            agent { label 'master' }
            steps {
                echo "Stage: Checkout"
                echo "Running on node: ${env.NODE_NAME}"
                echo "Checking out code on master node..."
                checkout scm
            }
        }

        stage('Build') {
            agent { label 'builder' }
            steps {
                echo "Stage: Build"
                echo "Running on node: ${env.NODE_NAME}"
                echo "Performing build on external agent..."
            }
        }

        stage('Test') {
            agent { label 'builder' }
            steps {
                echo "Stage: Test"
                echo "Running on node: ${env.NODE_NAME}"
                echo "Running tests on external agent..."
            }
        }

        stage('Deploy') {
            agent { label 'builder' }
            steps {
                echo "Stage: Deploy"
                echo "Running on node: ${env.NODE_NAME}"
                echo "Deploying on external agent..."
            }
        }
    }
}
