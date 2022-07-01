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
    stage('SonarQube Analysis') {
      steps {
      	withSonarQubeEnv(installationName: 'do-sonarqube') {
            withMaven(maven:'maven386') {
                sh 'mvn sonar:sonar'
            }
        }
      }
    }
    stage('SonarQube Gate') {
      steps {
        timeout(time: 2, unit: 'MINUTES') {
           waitForQualityGate abortPipeline: true
        }
      }
    }    
  }
}
