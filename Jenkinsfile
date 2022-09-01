pipeline {
  agent {
    node {
      label 'nodejs'
    }
  }
  stages {
    stage ('Creating a new  application') {
      steps {
        sh 'oc new-app --name firstimage quay.io/sundarrao/firstimage'
      }
    }
  }
  post {
    failure {
      echo 'FAILED'
      sh 'oc logs deployment/firstimage'
    }
    success {
      sh 'oc get pods'
      sh 'oc get all'
      echo 'SUCCESS'
    }
  }
}
