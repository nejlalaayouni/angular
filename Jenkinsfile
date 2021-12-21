pipeline {
    agent any;
    stages {
        stage('Restore') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run-script build'
            }
        }
        stage('Test') {
            steps {
                sh 'ng run-script test'
            }
        }        
        stage('Deploy') {
            steps {
                sh 'rm ../../apps/*'
                sh 'cp ./dist/apps/* ../../apps/'
            }
        }             
    }
}
