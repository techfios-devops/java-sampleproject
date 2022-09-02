pipeline {
  agent any
  tools {
    maven 'Maven' 
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
          deploy adapters: [tomcat8(credentialsId: 'tomcat_user', path: '', url:http://'ec2-35-175-143-173.compute-1.amazonaws.com')], contextPath: '', onFailure: false, war: '**/*.war' 
        }
      }
    }
  }
}
