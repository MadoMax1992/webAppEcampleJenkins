pipeline {
  agent any

  stages {
    stage ('Build') {
      steps {
        bat 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8(credentialsId: '5da75eee-0f2b-4a72-aaa5-4d269562a337', path: '', url: 'http://localhost:8080/')], contextPath: 'webAppExample', onFailure: false, war: '**/*.war'
        }
      }
    }
  }
}