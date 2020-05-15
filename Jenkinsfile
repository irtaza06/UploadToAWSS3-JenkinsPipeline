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
    }
}
