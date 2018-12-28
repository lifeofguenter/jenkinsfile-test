pipeline {

  agent {
    label 'dnb'
  }

  options {
    timestamps()
  }

  parameters {
    string(name: 'FOO', defaultValue: 'foo', description: 'Foobar?')
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
        echo "Hello ${params.FOO}"
      }
    }
  }
}
