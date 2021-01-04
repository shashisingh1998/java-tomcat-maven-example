pipeline {
 
	agent any

	tools {
		maven 'maven'
	} 
	stages {
 
		stage ('Git Checkout') {
 
			steps {
 
				git branch: 'develop',
 
				credentialsId: '7d947666-86fa-4882-bc71-e16f8b10afbf',
 
				url: 'https://github.com/shashisingh1998/java-tomcat-maven-example.git'
 
			}
 
		}
 
		stage ('Compile') {
 
			steps {
 
				sh 'mvn compile'
 
			}
 
		}
 
		stage ('Package') {
 
			steps {
 
				sh 'mvn package'
 
			}
 
		}
 
		stage ('Install') {
 
			steps {
 
				sh 'mvn install'
 
			}
 
		}
 
		stage ('Creat War File') {
 
			steps {
 
				sh 'java -jar target/dependency/webapp-runner.jar target/*.war'
 
			}
 
		}

		 stage ('Deploy War File') {

                        steps {

                                sh "sudo -i"

                        }

                }

 
		stage ('Deploy War File') {
 
			steps {
 
				sh "cp target/*.war apache-tomcat-9.0.41/webapps/"
 
			}
 
		}
 
	}
 
}
