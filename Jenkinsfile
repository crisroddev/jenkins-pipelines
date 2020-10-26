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
    }
}