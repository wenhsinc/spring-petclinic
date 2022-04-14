pipeline {
  agent any
  stages {
    stage('Package jar') {
      steps {
        timeout(time: 7, unit: 'MINUTES') {
          sh '''./mvnw package
'''
        }

      }
    }

    stage('Run ansible playbook') {
      steps {
        ansiblePlaybook(playbook: 'playbook.yml', disableHostKeyChecking: true, inventory: 'inventory', credentialsId: 'private-key', installation: 'Ansible')
      }
    }

  }
}