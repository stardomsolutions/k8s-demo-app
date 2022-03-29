pipeline {

  environment {
    NAMESPACE = "demoapp"
  }

  agent any
  parameters {
        string(name: "NAMESPACE", defaultValue: "default", description: "pass namespace name")
  }
  stages {

    stage('checkout code') {
      steps {
          checkout scm
		  }
    }
    stage('Update NS Value - We can step here if we need to update docker imnage tag in future') {
      steps {
          sh("sed -i 's#{{ NAMESPACE }}#${NAMESPACE}#' ./k8s-scripts/*.yaml")
      }
    }
    stage('Fetch K8S Creds') {
      steps {
           sh("echo 'Fecth K8S creds here'")
		   }
    }
    stage('Deploy to K8S') {
      steps {
           sh("echo 'Deploy to K8S cluster here'")
		   }
    }

  }
}
