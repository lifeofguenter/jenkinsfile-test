#!groovy

@Library('foobar@labfoo') _

pipeline {

  agent {
    label 'dnb'
  }

  options {
    timestamps()
  }
  
  triggers {
    issueCommentTrigger('\\s*please build\\s*')
    //cron('*/2 * * * *')
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
        foobar this
      }
    }

    stage('Conditional') {
      when {
        expression {
          return foobar this
        }
      }
      steps {
        helloWorld()
      }
    }
  }

}
