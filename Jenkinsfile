pipeline {
  agent any
  stages {
    stage('Run ansible playbook') {
      steps {
        ansiblePlaybook(playbook: 'playbook.yml', disableHostKeyChecking: true, inventory: 'inventory', credentialsId: 'private-key', installation: 'Ansible')
      }
    }

  }
}