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
			environment {
				ANYPOINT_CREDENTIALS = credentials('anypointPlatform')
			}
            steps {
                echo 'Deploying....'
				bat 'mvn package -Ptest deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW}'
            }
        }
  }
}