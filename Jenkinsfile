pipeline {
  agent any
  stages {
    stage('Init Terraform') {
      steps {
        bat 'terraform init'
      }
    }
    stage('Validate & Plan') {
      steps {
        bat 'terraform validate'
        bat 'terraform plan -out=plan.txt'
      }
    }
  }
  post {
    success {
      archiveArtifacts artifacts: 'plan.txt'
      echo ' Plan Terraform simulado generado'
    }
  }
}
