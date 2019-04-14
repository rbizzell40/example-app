node {
       def app

       stage('Clone repository') {
               checkout scm
       }

       stage('Build image') {
               app = docker.build('rbizzell40/example-app')
       }

       stage('Push image') {
               docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                       app.psuh('latest')
               }
       }
}