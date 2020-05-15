pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello World!"'
                sh '''
                  echo "Multiline shell steps wroks too"
                  ls -lah
                '''
            }
        }
        stage('Lint HTML') {
            steps {
                sh tidy -q -e *.html
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(region:'eu-central-1',credentials:'aws-static')
            {
                s3Upload(file:'index.html', bucket:'aws-static-bucket')
            }

            }
        }
    }
}
