pipeline {
    agent any

    stages {
        stage('Pulling Code From SCM') {
            steps {
                echo 'Pulling....'
            }
        }
        stage('Deploy') {
            steps {
                input message: 'Do you want to Deploy website? (Click "Proceed" to continue)'
                sh 'aws s3 cp . s3://acloudxpert --recursive'
            }
        }
        stage('Setting Permission') {
            steps {
                sh 'aws s3 website s3://acloudxpert/ --index-document index.html --error-document error.html'
            }
        }
    }
}
