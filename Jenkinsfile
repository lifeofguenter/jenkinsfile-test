#!groovy

@Library('foobar@master') _

pipeline {

  agent {
    label 'debian-9'
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

    //stage('Test') {
    //  steps {
    //    helloWorld()
    //    sh 'printenv'
    //  }
    //}

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
