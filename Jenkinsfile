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
                sh 'aws s3 cp . s3://s307082022 --recursive'
            }
        }
        stage('Setting Permission') {
            steps {
                sh 'aws s3 website s3://s307082022/ --index-document index.html --error-document error.html'
            }
        }
    }
}
