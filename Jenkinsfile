pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "Start build"'
      }
    }

    stage('SonarQube') {
      steps {
        withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'SonarQube token', envOnly: true)
      }
    }

  }
}