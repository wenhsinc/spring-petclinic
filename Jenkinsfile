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

    stage('Run jar') {
      steps {
        sh 'java -jar target/*.jar'
      }
    }

  }
}