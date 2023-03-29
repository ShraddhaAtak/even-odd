pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t even-odd-number-generator .'
      }
    }
    stage('Test') {
      steps {
        sh 'docker run even-odd-number-generator'
      }
    }
    stage('Deploy') {
      steps {
        sh 'kubectl apply -f deployment.yaml'
        sh 'kubectl apply -f service.yaml'
      }
    }
  }
}
