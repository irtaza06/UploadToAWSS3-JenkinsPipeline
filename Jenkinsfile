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

        dir('/home/irtaza06/Downloads/DevOps/CICD/'){

            pwd(); //Log current directory

            withAWS(region:'eu-central-1',credentials:'aws-static') {

                 def identity=awsIdentity();//Log AWS credentials

                // Upload files from working directory 'dist' in your project workspace
                s3Upload(bucket:"aws-static-bucket", workingDir:'static', includePathPattern:'**/*');
            }

        };
    }
    }
}
