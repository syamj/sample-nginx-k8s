pipeline {
  agent any
  stages {
    stage('Deploy to K8s') {
      steps {
        withKubeConfig([credentialsId: 'kube-config']) {
	sh kubectl apply -f nginx/*
	}
      }
    }
  }
}
