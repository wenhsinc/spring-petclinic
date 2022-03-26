pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Initiating maven build'
        withSonarQubeEnv(installationName: 'SonarQube Scanner', credentialsId: 'SonarQube token') {
          sh 'mvn clean package sonar:sonar'
        }

      }
    }

    stage('Create jar') {
      steps {
        sh 'java -jar -Dserver.port=7000 build/libs/spring-petclinic-2.6.0.jar'
      }
    }

  }
}