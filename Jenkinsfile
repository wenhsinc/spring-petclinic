pipeline {
  agent any
  stages {
    stage('SonarQube analysis') {
      steps {
        withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'SonarQube token')
        waitForQualityGate(credentialsId: 'SonarQube token', abortPipeline: true)
      }
    }

    stage('Build') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Create JAR') {
      steps {
        sh 'java -jar target/spring-petclinic-2.1.0.jar'
      }
    }

  }
}