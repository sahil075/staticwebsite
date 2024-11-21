pipeline {
    agent any 
    environment {
        AWS_DEFAULT_REGION = "ap-south-1"
        THE_BUTLER_SAYS_SO = credentials('Test1')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building stage"
            }
        }
        stage('Test') {
            steps {
                echo "Testing stage"
            }
        }
        stage('Deploy to S3') { 
            steps { 
                echo "Deploying to S3"
                echo "AWS Region: ${AWS_DEFAULT_REGION}"
                echo "Deploying file: ./index.html"
                sh 'aws s3 cp ./index.html s3://botshotsahil.live --region ap-south-1'
            } 
        }
    }
    post {
        success {
            echo "Deployment successful"
        }
        failure {
            echo "Deployment failed"
        }
    }
}

