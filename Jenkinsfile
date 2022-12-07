pipeline {

  agent any
  
  stages {
    stage('Build') {
      steps {
            bat 'mvn clean install'
      }
    }

    stage('Test') {
      steps {
          echo "****** munit test cases execution******"
      }
    }

    stage('Deployment') {
     
      steps {
            bat ''mvn package -Ptest deploy -DmuleDeploy'
      }
    }
  }
}