pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/manojreddy-m/Ec2_S3_deploy_GHUB.git'
            }
        }

        stage('Deploy to S3') {
            steps {
                sh '''
                    aws s3 sync . s3://jenkins-s3-030303/ \
                    --exclude ".git/*" \
                    --exclude "Jenkinsfile"
                '''
            }
        }
    }
}
