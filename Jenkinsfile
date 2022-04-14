pipeline {
  agent any
  stages {
    stage('Run ansible playbook') {
      steps {
        ansiblePlaybook(playbook: 'playbook.yml', disableHostKeyChecking: true, inventory: 'dev.inv')
      }
    }

  }
}