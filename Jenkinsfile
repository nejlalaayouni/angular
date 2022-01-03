pipeline {
  agent any
    
  tools {nodejs "Node-16.13"}
    
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/nejlalaayouni/angular.git'
      }
    }
     
    stage('Build') {
      steps {
        sh 'npm install'
         
      }
    }  
    
    stage('Start') {
      steps {
        sh 'npm run'
      }
    }
    stage('TEST') {
      steps {
        sh 'curl -X POST http://127.0.0.1:4200'
      }
    }
  }
  
}

