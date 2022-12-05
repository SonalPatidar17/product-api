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
				bat 'mvn test'
            }
        }
        stage('Deploy CloudHub') {
			environment {
				ANYPOINT_CREDENTIALS = credentials('anypointPlatform')
			}
            steps {
                echo 'Deploying....'
				bat 'mvn package deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denvironment=dev -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2'
            }
        }
    }
}