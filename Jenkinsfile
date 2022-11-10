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
        sh 'mvn clean package'
        stash(name: 'build-test-artifacts', includes: '**/ target/surefire-reports/TEST-*.xml,target/*.jar')
      }
    }

  }
}