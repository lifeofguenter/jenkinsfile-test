#!groovy

@Library('foobar@labfoo') _

pipeline {

  agent {
    label 'debian-9'
  }

  options {
    timestamps()
  }
  
  triggers {
    issueCommentTrigger('\\s*please build\\s*')
    cron('*/2 * * * *')
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
        foobar()
      }
    }

    stage('Conditional') {
      //when {
      //  expression {
      //    return foobar(this)
      //  }
      //}
      steps {
        helloWorld()
      }
    }
  }

}
