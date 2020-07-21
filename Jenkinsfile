pipeline {
    agent any

    stages {
        stage('Validating CFT') {
            steps {
                echo 'Validating CFT..'
                sh "aws cloudformation validate-template --template-body file://deployEC2CFT.json"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh "aws cloudformation crate-stack --stack-name jenkins-ec2-cft --template-body file://deployEC2CFT.json --region 'us-east-1' "
            }
        }
    }
}
