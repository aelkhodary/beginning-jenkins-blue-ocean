pipeline {
  agent {
    node {
      label 'doker'
    }

  }
  stages {
    stage('Build & Test') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        sh 'echo \'This is a test\' > data.txt'
      }
    }

  }
}