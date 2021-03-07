pipeline {
  agent any
  stages {
    stage('Build and push image with Container Builder') {
      steps {
          sh "docker build  -t nginx-test:$BUILD_ID ."
        }
      }
    stage('Apply Kubernetes Files') {
      steps {
          withKubeConfig([credentialsId: 'kubeconfig']) {
          sh ' docker rmi nginx-test:$BUILD_ID' 
          sh 'kubectl apply -f nginx/'

        }
      }
  }
}
}
