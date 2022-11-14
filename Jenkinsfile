pipeline {
  agent any
  stages {
    stage('Build & Test') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        sh 'echo \'This is a test\' > data.txt'
        stash(name: 'build-test-artifacts', includes: '**/ target/surefire-reports/TEST-*.xml,target/*.jar')
      }
    }

  }
}