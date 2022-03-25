pipeline {
  agent any
  stages {
    stage('Scan with SonarQube') {
      steps {
        withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'SonarQube token')
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