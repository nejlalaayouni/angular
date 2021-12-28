pipeline {
  agent any
     tools {nodejs "Node-16.13"}

    stages {
        stage('Build') {
            steps {
                nodejs(nodeJSInstallationName: 'Node 6.x', configId: '<config-file-provider-id>') {
                    sh 'npm config ls'
                }
            }
        }
    }
}
