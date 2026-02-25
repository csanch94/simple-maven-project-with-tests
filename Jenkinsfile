pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Build & Test') {
      steps {
        bat 'mvn -B -ntp -Dmaven.test.failure.ignore verify'
      }
    }
  }

  post {
    always {
      junit '**/target/surefire-reports/TEST-*.xml'
    }
  }
}
