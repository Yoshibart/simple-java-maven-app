pipeline{
  agent any
  tools{
    maven 'Maven_3'
  }
  stages {
    stage('Checkout'){
      steps {
        checkout scm
      }
    }
    stage('Build and Test'){
      steps{
        sh 'mvn clean verify'
      }
    }
  }
    post {
      always{
        publishHTML(target: [
          reportDir: 'target/site/jacoco',
          reportFiles: 'index.html',
          reportName: 'JaCoCo Code Coverage',
          keepAll: true,
          alwaysLinkToLastBuild: true
          ])
      }
    }
}
