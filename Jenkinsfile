pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        withMaven(maven: 'maven386') {
          sh 'mvn clean install'
        }
      }
    }
  }
}
