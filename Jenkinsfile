#!groovy

@Library('foobar@master') _

pipeline {

  agent {
    label 'dnb'
  }

  options {
    timestamps()
  }
  
  triggers {
    issueCommentTrigger('\\s*please build\\s*')
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
      helloWorld
    }
  }

}
