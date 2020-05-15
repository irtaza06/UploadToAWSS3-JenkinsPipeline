pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
            withAWS(region:'eu-central-1',credentials:'jenkins') {

                 def identity=awsIdentity();//Log AWS credentials

                // Upload files from working directory 'dist' in your project workspace
                s3Upload(bucket:"aws-static-bucket", workingDir:'./', includePathPattern:'**/*');
            }
            }
        }
    }
}
