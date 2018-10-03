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
    cron('* * * * *')
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Test') {
      steps {
        helloWorld()
        sh 'printenv'
      }
    }

    stage('Conditional') {
      when {
        expression {
          return foobar()
        }
      }
      steps {
        helloWorld()
      }
    }
  }

}
