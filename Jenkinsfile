pipeline {
  agent any
  stages {
    stage('Static analysis and Build') {
      steps {
        echo 'Initiating maven build'
        withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'SonarQube Secret') {
          sh 'mvn clean package sonar:sonar'
        }

      }
    }

    stage('Create jar') {
      steps {
        sh 'java -jar target/spring-petclinic-2.1.0.jar '
      }
    }

  }
}