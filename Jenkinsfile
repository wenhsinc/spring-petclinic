pipeline {
  agent any
  stages {
    stage('Create JAR') {
      steps {
        sh '''mvn package
java -jar target/spring-petclinic-2.1.0.jar'''
      }
    }

  }
}