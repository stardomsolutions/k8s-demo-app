pipeline {

  environment {
    NAMESPACE = "demoapp"
  }

  agent any
  stages {

    stage('Update NS Value') {
      steps {
        container('kubectl') {
          sh("sed -i 's#{{ NAMESPACE }}#${NAMESPACE}#' ./k8s-scripts/*.yaml")
        }
      }
    }

  }
}
