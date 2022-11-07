pipeline {
  agent {
    node {
      label 'master'
    }

  }
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