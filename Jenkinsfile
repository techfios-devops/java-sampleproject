pipeline {
  agent any
  tools {
    maven 'M2_HOME' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8(credentialsId: 'tomcat_user', path: '', url: 'http://35.175.143.173:8080')], contextPath: '', onFailure: false, war: '**/*.war' 
        }
      }
    }
  }
}
