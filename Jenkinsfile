pipeline {
  agent any
  stages {
    stage('Build Application') { 
      steps {
        bat 'mvn clean install'
      }
    }
 	stage('Test') { 
      steps {
        echo 'Test Appplication...' 
      
      }
    }
 	
   
	stage('Deploy CloudHub2.0') { 
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
            
      steps {
        echo 'Deploying only because of code commit...'
        echo 'Deploying to dev environent....'
        bat 'mvn clean deploy -Pdev -DmuleDeploy'
      }
	  
	}
  }
}