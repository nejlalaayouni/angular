pipeline {
  agent any
    
  tools {nodejs "Node-16.13"}
  
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/nejlalaayouni/angular.git'
      }
    }
     
    stage('Install node modules'){
      steps {
        sh 'npm install '
         
      }
    }  
    
  stage('Test'){
      steps {
        sh 'npm run test-headless'
      }
    }
  stage('Build'){
      steps {
        sh 'npm run build --prod'
      }
    }
  }
  
}

