pipeline {
    agent any

    stages {
        stage('Build Application') {
            steps {
                echo 'Building..'
				bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
				  }
        }
        stage('Deploy CloudHub') {
			 steps {
                echo 'Deploying....'
				bat 'mvn package -Ptest deploy -DmuleDeploy            }
        }
    }
}