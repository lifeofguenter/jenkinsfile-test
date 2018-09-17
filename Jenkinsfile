pipeline {

  agent {
    label 'dnb'
  }

  options {
    timestamps()
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage ('Test') {
      steps {
        sh 'printenv'
      }
    }
  }

}
