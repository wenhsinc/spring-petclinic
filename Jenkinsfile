pipeline {
  agent any
  stages {
    stage('Build and  SonarQube analysis') {
      steps {
        withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'SonarQube token') {
          sh 'mvn clean package sonar:sonar'
        }

      }
    }

    stage('Create JAR') {
      steps {
        sh 'java -jar target/spring-petclinic-2.1.0.jar'
      }
    }

  }
}