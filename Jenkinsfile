pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                withAWS(credentials: 'aws-static') {
                    s3Upload(file:'index.html', bucket:'udacity-jenkins-project', path: 'index.html', verbose:true)
                }
            }
        }
    }
}
