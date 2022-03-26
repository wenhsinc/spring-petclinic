pipeline {
  agent any
  stages {
    stage('SonarQube Static analysis') {
      steps {
        echo 'Initiating maven build'
        withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'SonarQube Secret') {
          sh 'mvn clean package sonar:sonar'
        }

      }
    }

    stage('Package jar') {
      steps {
        timeout(time: 7, unit: 'MINUTES') {
          sh '''./mvnw package

'''
        }

      }
    }

  }
}