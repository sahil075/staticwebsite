pipeline{
    agent any 
    environment {
    AWS_DEFAULT_REGION = "ap-south-1"
    THE_BUTLER_SAYS_SO = credentials('jenkins-aws')
    }
    stages {
        stage ('Build'){
            steps {
                echo "Building stage"
            }
        }
        stage ('Test'){
            steps {
                echo "Testing stage"

            }
        }
        stage ('Deploy to S3'){ 
            steps{ 
                echo "Deploying" 
                sh ' aws s3 cp ./index.html s3://botshotsahil.live '
            } 
        }

    }

    post{
        success {
            echo "success"
        }
        failure {
            echo "failure"
        }
    }
}
