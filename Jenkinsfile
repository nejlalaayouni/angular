pipeline {
  agent any
     tools {nodejs "Node-16.13"}

  stages {
      stage('git') {
         steps {
            git 'https://github.com/nejlalaayouni/angular.git'
           
         }
      }
     
    stage('Build') {
         steps {
            echo 'Building..'
            dir('angular') {
               bat 'npm run ng -- build --prod --baseHref=/angular/ -optimization=true'
            }
         }
      }
 
   stage('Deploy') {
         steps {
            echo 'Deploying....'
            ftpPublisher paramPublish: null, masterNodeName: '', alwaysPublishFromMaster: true, continueOnError: false, failOnError: true, publishers: [
               [configName: 'mattdailey.net', verbose: true, transfers: [
                  [asciiMode: false, cleanRemote: true, excludes: '', flatten: false, makeEmptyDirs: tur, noDefaultExcludes: false, patternSeparator: '[, ]+',
                     remoteDirectory: "webapp", removePrefix: "webapp/dist", remoteDirectorySDF: false, sourceFiles: 'webapp/dist/**'
                  ]
               ], usePromotionTimestamp: false, useWorkspaceInPromotion: false]
            ]
         }
      }
   }
   post {
      success {
         slackSend(color: '#00FF00', message: "Build Successful")
      }
      failure {
         slackSend(color: '#FF0000', message: "Build Failed")
      }
   }
}
