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
        timeout(time: 7, unit: 'MINUTES') {
          sh '''./mvnw package
java -jar -Dserver.port=7000 target/*.jar'''
        }

      }
    }

    stage('End') {
      steps {
        sh 'echo \'Success!\''
      }
    }

  }
}