node {
    stage('Checkout') {
        checkout scm
    }
    stage('Build') {
        
            sh 'npm install'
            
        }
        
    
    stage('Test') {
       
            sh 'ng test --progress false --watch false'
        
      
    }
}
