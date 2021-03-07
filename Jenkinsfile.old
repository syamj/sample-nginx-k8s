pipeline {
  agent any
  stages {
    stage('Deploy to K8s') {
      steps {
        withKubeConfig([credentialsId: 'kubeconfig']) {
	sh kubectl apply -f nginx/*
	}
      }
    }
  }
}
