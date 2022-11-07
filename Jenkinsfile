pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        withMaven(maven: 'maven') {
          sh 'mvn clean install'
        }

      }
    }

    stage('Results') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}