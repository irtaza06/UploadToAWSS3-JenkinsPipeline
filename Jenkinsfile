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
    stage('Upload') {

            withAWS(region:'eu-central-1',credentials:'aws-static') {

                 def identity=awsIdentity();//Log AWS credentials

                // Upload files from working directory 'dist' in your project workspace
		s3Upload(file:'index.html', bucket:'aws-static-bucket', path:'/home/irtaza06/Downloads/DevOps/CICD/static/index.html')
            }

        }
    }
    }
}
