pipeline {
  agent any
  stages {
    stage('Run ansible playbook') {
      steps {
        ansiblePlaybook(playbook: 'playbook.yml', disableHostKeyChecking: true, inventory: 'inventory', inventoryContent: '[server] 127.0.0.1 ansible_port=2222 ansible_user=vagrant', credentialsId: 'private-key', installation: 'Ansible')
      }
    }

  }
}