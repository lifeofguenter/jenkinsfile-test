@Library('jenkins-pipeline-library@add-on') _

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
    }

    stage ('On') {
      steps {
        on.pr("echo '[pr] hello world!'")
        on.master("echo '[master] hello world!'")
      }
    }
  }

}
