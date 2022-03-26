pipeline {
  agent any
  stages {
    stage('build && SonarQube analysis') {
      steps {
        withSonarQubeEnv('SonarQube') {
          withMaven(maven: 'Maven 3.6.3') {
            sh 'mvn clean package sonar:sonar'
          }

        }

      }
    }

    stage('Quality Gate') {
      steps {
        timeout(time: 1, unit: 'HOURS') {
          waitForQualityGate true
        }

      }
    }

  }
}