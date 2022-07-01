pipeline {
  agent any
  stages {
    stage('sonar qube') {
      steps {
      	        withSonarQubeEnv(credentialsId: 'sq-jk-ppl-token', installationName: 'do-sonarqube') {
                	withMaven(maven:'maven386') {
                        sh 'mvn -e sonar:sonar'
                    }
                }
      }
    }
  }
}
