pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('build') {
      steps {
        withMaven(globalMavenSettingsConfig: 'M3') {
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