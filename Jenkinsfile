node {
    stage('Checkout') {
        checkout scm
    }
    stage('Build') {
        
            sh 'npm install'
            
        }
        
    }
    stage('Test') {
        docker.image('trion/ng-cli-karma').inside {
            sh 'ng test --progress false --watch false'
        }
        junit '**/test-results.xml'
    }
}
