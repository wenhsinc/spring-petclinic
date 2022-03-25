pipeline {
  agent any
  stages {
    stage('SonarQube') {
      steps {
        withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'SonarQube token') {
          sh 'mvn clean package sonar:sonar'
        }

      }
    }

  }
}