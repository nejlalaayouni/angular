pipeline {
  agent any
     tools {nodejs "Node-16.13"}
  
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/monadevOp/angular.git'
      }
    }
     
    stage('Build') {
      steps {
        sh 'npm install npm@latest -g'
         
      }
    }  
    
    stage('Start') {
      steps {
        sh 'npm install -g @angular/cli'
      }
    }
    stage('TEST') {
      steps {
        sh 'ng serve POST http://127.0.0.1:4200'
      }
    }
  }
  
}
