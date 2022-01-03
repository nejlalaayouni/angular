pipeline {
  agent any

  
  stages {
        
    stage('checkout SCM') {
      steps {
        git 'https://github.com/nejlalaayouni/angular.git'
      }
    }
     
    stage('Install node modules')
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
}
