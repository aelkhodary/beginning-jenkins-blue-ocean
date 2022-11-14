pipeline {
  agent none
  stages {
    stage('Build & Test') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        sh 'mvn -Dmaven.test.failure.ignore clean package'
        stash(name: 'Build-test-artifacts', includes: '**/target/surefire-reports/TEST-*.xml,target/*.jar')
      }
    }

    stage(' Report & Publish') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        unstash 'Build-test-artifacts'
        junit '**/target/surefire-reportss/TEST-*. xml'
        archiveArtifacts(artifacts: '*/Ch03/example-maven-project/target/*.jar', onlyIfSuccessful: true)
      }
    }

  }
}