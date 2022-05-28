pipeline {
  agent { label 'linux'}
  options {
    skipDefaultCheckout(true)
  }
  stages{
    stage('clean workspace') {
      steps {
        cleanWs()
      }
    }
    stage('checkout') {
      steps {
        checkout scm
      }
    }
    stage('terraform-init') {
      steps {
        sh 'terraform init'
      }
    }
    stage('terraform-plann') {
      steps {
        sh 'terraform plan'
      }
    }
    stage('terraform') {
      steps {
        sh 'terraform apply -auto-approve'
      }
    }
  }
  post {
    always {
      cleanWs()
    }
  }
}
