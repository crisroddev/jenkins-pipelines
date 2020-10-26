pipeline {
    agent any
    stages {
        stage('Start-Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works to"
                    ls -lah
                '''
            }
        }
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload-to-AWS'){
            steps {
                withAWS(region: 'us-east-1', withCredentials: 'static'){
                    sh 'echo "Uploading file to AWS S3 Bucket"'
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html',  bucket:'jenkins-practice')
                }
                
            }
        }
    }
}