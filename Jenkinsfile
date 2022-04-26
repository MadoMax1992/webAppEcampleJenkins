pipeline {
  agent any

  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: 'deployer', path: '', url: 'http://localhost:8080/')], contextPath: 'webAppExample', onFailure: false, war: '**/*.war'
        }
      }
    }
  }
}